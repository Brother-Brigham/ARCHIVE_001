## Desktop Compliance Audit Report
*Report drafted with Google Gemini 3.1 Pro*

**System Audited:** Arch Linux Desktop/Laptop

**Audit Tool:** Hermes Agent

**Framework:** CIS Distribution Independent Linux Benchmarks

### Audit Summary & Reflection

Based on the audit of this Arch Linux system, the **biggest gaps in compliance** lie in system visibility, host integrity, and network hardening. Specifically, the complete lack of active logging (`auditd` is installed but inactive), the absence of a filesystem integrity checker like `AIDE`, and missing Mandatory Access Controls (SELinux/AppArmor) leave the system largely blind to unauthorized changes or malicious activity. **What surprised me** was that IP forwarding was enabled and Reverse Path Filtering was disabled; these default network configurations unnecessarily expand the attack surface for a standard desktop machine. Furthermore, it is surprising to see `auditd` installed on the system but entirely disabled. **Based on these findings, the system is currently insecure** for a hardened or corporate environment. While it successfully implements some strong foundational security measures—such as using YESCRYPT for password hashing, disabling SSH root logins, and disabling unnecessary Samba shares—the permissive default umask (022), lack of password expiration rules, and missing auditing/integrity safeguards mean the system would struggle to prevent, detect, or contain a compromise.

### Detailed Audit Findings

The following table details the results of the compliance checks conducted against the system.

|**CIS ID**|**Category**|**Control**|**Status**|
|---|---|---|---|
|**5.3.1**|Account/password|Password creation requirements configured|**PASS**|
|**5.3.2**|Account/password|Lockout for failed password attempts configured|**PASS**|
|**5.3.3**|Account/password|Password reuse is limited|**FAIL**|
|**5.3.4**|Account/password|Password hashing algorithm is SHA-512|**PASS**|
|**5.4.1.1**|Account/password|Password expiration is 365 days or less|**FAIL**|
|**5.4.1.4**|Account/password|Inactive password lock is 30 days or less|**FAIL**|
|**5.4.4**|Account/password|Default user umask is 027 or more restrictive|**FAIL**|
|**4.1.2**|Audit/logging|`auditd` is installed|**FAIL** _(Installed but inactive)_|
|**4.1.3**|Audit/logging|`auditd` service is enabled|**FAIL**|
|**4.1.19**|Audit/logging|Audit configuration is immutable|**UNKNOWN**|
|**1.3.1**|Antivirus/host integrity|AIDE is installed|**FAIL**|
|**1.3.2**|Antivirus/host integrity|Filesystem integrity is regularly checked|**FAIL**|
|**3.1.1**|Firewall/network|IP forwarding is disabled|**FAIL**|
|**3.2.7**|Firewall/network|Reverse Path Filtering is enabled|**FAIL**|
|**1.6.1.1**|Privilege/UAC|SELinux or AppArmor installed|**FAIL**|
|**5.2.10**|Privilege/UAC|SSH root login is disabled|**PASS**|
|**2.2.1**|System services|Time synchronization is in use|**PASS**|
|**2.2.15**|System services|MTA is configured for local-only mode|**UNKNOWN**|
|**2.2.12**|File sharing/removable|Samba is not enabled if unnecessary|**PASS**|
|**1.1.23**|File sharing/removable|USB Storage disabled|**NOT CHECKED**|
|**1.1.22**|File sharing/removable|Automount disabled|**NOT CHECKED**|
|**1.1.21**|Filesystem hardening|Sticky bit set on all world-writable directories|**NOT CHECKED**|
|**1.1.6-10**|Filesystem hardening|`/tmp`, `/var/tmp` mount options/size|**NOT CHECKED**|

**Note:** _This audit was conducted in a read-only capacity. No changes or remediations were made to the system during this evaluation._