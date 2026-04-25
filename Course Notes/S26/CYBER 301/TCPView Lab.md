Adapted to Arch Linux with Claude Sonnet 4.6.

# Network Connection Monitoring Lab — Arch Linux

**Tool:** `ss` + `watch` + `lsof` + `whois`

---

## 🧭 Part 1: Exploring the Live View

### 1. Observe the Live View

Run the following command to get a continuously refreshing view of all active connections, equivalent to TCPView's main window:

```bash
watch -n 2 'sudo ss -tup -o state established \
  | awk "NR==1 || /ESTAB/" \
  | column -t'
```

This gives you a live-updating table. Here is how the columns map to TCPView:

|TCPView Column|What to look at in the output|
|---|---|
|Process|Inside `users:(("name",...))` at the end of each row|
|PID|The `pid=` value inside `users:((...))`|
|Protocol|The leftmost column (`tcp` or `udp`)|
|Local Address|The `Local Address:Port` column|
|Remote Address|The `Peer Address:Port` column|
|State|The `State` column (`ESTAB`, `LISTEN`, `CLOSE-WAIT`, etc.)|

**Color coding equivalent:** While `ss` does not color-code output natively, you can simulate it. Run this instead to highlight new vs. closed connections over time:

```bash
watch -n 2 --color 'sudo ss -tup | grep --color=always -E "ESTAB|LISTEN|CLOSE-WAIT|TIME-WAIT|.*"'
```

- `ESTAB` = active connection (green in TCPView)
- `TIME-WAIT` / `CLOSE-WAIT` = closing connection (red in TCPView)
- `LISTEN` = waiting for connections (neutral/grey in TCPView)

---

### 2. Sort by Process

To identify which processes are making the most outbound connections, run:

```bash
sudo ss -tp state established | grep -oP 'users:\(\("\K[^"]+' | sort | uniq -c | sort -rn
```

This prints a ranked list of process names by number of active outbound connections, equivalent to clicking the **Process** column header in TCPView to sort.

To see the full connection details sorted by process name:

```bash
sudo ss -tp state established | sort -k6
```

---

### 3. Common Ports Activity

Run each command below to identify which processes are using each port of interest, equivalent to visually scanning TCPView's **Local Port** or **Remote Port** column:

**Port 80 — HTTP:**

```bash
sudo lsof -i :80
```

**Port 443 — HTTPS:**

```bash
sudo lsof -i :443
```

**Port 53 — DNS:**

```bash
sudo lsof -i :53
```

**Port 25 — SMTP:**

```bash
sudo lsof -i :25
```

**All four at once:**

```bash
sudo lsof -i :80,443,53,25
```

The `COMMAND` column in the output tells you which process is using that port, equivalent to TCPView's **Process** column.

---

## 🔍 Part 2: Identify Suspicious Activity

### 1. Simulate Normal Traffic

Open a web browser and navigate to a few secure (HTTPS) websites. Then, in a separate terminal, run the live view command to watch connections populate in real time — equivalent to watching TCPView's list update as you browse:

```bash
watch -n 1 'sudo ss -tp state established'
```

As you navigate to new sites, you will see new `ESTAB` rows appear with your browser's process name and the remote IP addresses of each site. When a connection closes, the row will disappear or transition to `TIME-WAIT`.

---

### 2. Spot the Unusual

**Are there connections to unfamiliar IP addresses?**

Extract all unique remote IPs from your active connections and review them:

```bash
sudo ss -tp state established | awk '{print $5}' | cut -d: -f1 | sort -u
```

Cross-reference any unfamiliar IPs using `host` or `dig`:

```bash
host 203.0.113.42
dig -x 203.0.113.42
```

**Are there processes you don't recognize?**

List every process currently holding a network connection:

```bash
sudo lsof -i | awk 'NR>1 {print $1}' | sort -u
```

Review the list and note any process names you don't recognize.

**Any traffic over uncommon ports?**

Scan for connections on suspicious or non-standard ports:

```bash
sudo ss -tp | grep -E ':6666|:31337|:4444|:1337|:9999'
```

You can add additional port numbers to the pattern as needed.

---

### 3. Right-Click Analysis

In TCPView you right-click a process to access **Properties** and **Whois**. Here is how to replicate both:

**"Properties" → Investigate a process by PID:**

First, get the PID of the process you want to investigate from your `ss` or `lsof` output. Then run:

```bash
# See the full executable path
ls -l /proc/<PID>/exe

# See the exact command used to launch the process
cat /proc/<PID>/cmdline | tr '\0' ' ' && echo

# See all files and connections this process has open
sudo lsof -p <PID>
```

Replace `<PID>` with the actual process ID number.

**"Whois" → Look up a remote IP address:**

```bash
whois <REMOTE_IP>
```

Replace `<REMOTE_IP>` with the IP address from the remote address column of your `ss` or `lsof` output. The output will show you the registered owner, organization, and country of that IP — the same information TCPView's Whois dialog provides.