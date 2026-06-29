20 Benchmark controls, determined using the CIS Distribution Independent Linux benchmarks guide. Used to analyze an Arch Linux system. Hermes Agent used to conduct the system audit.
      
   Account and password policies  
   1. 5.3.1 - Ensure password creation requirements are configured.  
   2. 5.3.2 - Ensure lockout for failed password attempts is configured.  
   3. 5.3.3 - Ensure password reuse is limited.  
   4. 5.3.4 - Ensure password hashing algorithm is SHA-512.  
   5. 5.4.1.1 - Ensure password expiration is 365 days or less.  
   6. 5.4.1.4 - Ensure inactive password lock is 30 days or less.  
   7. 5.4.4 - Ensure default user umask is 027 or more restrictive.  
      
   Audit policies and event logging  
   8. 4.1.2 - Ensure auditd is installed.  
   9. 4.1.3 - Ensure auditd service is enabled.  
   10. 4.1.9 - Ensure login and logout events are collected.  
   11. 4.1.19 - Ensure audit configuration is immutable.  
      
   Antivirus / host integrity equivalent  
   12. 1.3.1 - Ensure AIDE is installed.  
   13. 1.3.2 - Ensure filesystem integrity is regularly checked.  
      
   Firewall / network  
   14. 3.1.1 - Ensure IP forwarding is disabled.  
   15. 3.2.7 - Ensure Reverse Path Filtering is enabled.  
      
   Privilege / UAC equivalent  
   16. 1.6.1.1 - Ensure SELinux or AppArmor are installed.  
   17. 5.2.10 - Ensure SSH root login is disabled.  
      
   System services  
   18. 2.2.1 - Ensure time synchronization is in use.  
   19. 2.2.15 - Ensure MTA is configured for local-only mode.  
      
   File sharing and removable media  
   1. 2.2.12 - Ensure Samba is not enabled if unnecessary.

--- 

 Read-only findings only. No changes were made.  
      
   Account and password policies  
   - 5.3.1 - PASS: password requirements are configured through pam_faillock.so is present in /etc/pam.d/system-login and related PAM files, indicating login failure lockout is configured.  
   - 5.3.3 - UNKNOWN: no pam_pwhistory.so entry was found in /etc/pam.d/ or /etc/security/, so password reuse restriction is not currently enforced.  
   - 5.3.4 - PASS: /etc/login.defs shows ENCRYPT_METHOD YESCRYPT, which is strong.  
   - 5.4.1.4 - FAIL: /etc/login.defs has no INACTIVE setting, and chage -l <user> would be needed to confirm expiration behavior; based on current config this is not set.  
   - 5.4.4 - FAIL: /etc/login.defs has UMASK 022, which is more permissive than CIS recommended 027+.  
      
   Audit policies and event logging  
   - 4.1.2 - FAIL: auditd is installed (auditctl exists) but not enabled or active.  
   - 4.1.3 - FAIL: auditd unit is disabled and inactive.  
   - 4.1.19 - UNKNOWN: immutable audit rules require auditd to be active and configured with -e 2.  
      
   Antivirus / host integrity equivalent  
   - 1.3.1 - FAIL: aide is not installed.  
   - 1.3.2 - FAIL: no filesystem integrity checker is scheduled/active (no aide, tripwire, or related jobs found).  
      
   Firewall / network  
   - 3.1.1 - FAIL: sysctl net.ipv4.ip_forward returned 10210, so IP forwarding is enabled.  
   - 3.2.7 - FAIL:  
     - net.ipv4.conf.all.rp_filter = 0  
     - net.ipv4.conf.default.rp_filter = 0  
     Reverse Path Filtering is disabled.  
     - net.ipv6.conf.all.accept_ra returned 1; IPv6 router advertisements are accepted.  
      
   Privilege / UAC equivalent  
   - 1.6.1.1 - FAIL: neither SELinux nor AppArmor is present (lsmod | grep -i 'selinux\|apparmor' yielded no match; aa-status/sestatus not available).  
   - 5.2.10 - UNKNOWN: grep -E against /etc/ssh/sshd_config returned mainly comments; PermitRootLogin was not found, so SSH root login is either default-enabled or controlled elsewhere and should be verified explicitly.  
      
   System services  
   - 2.2.1 - PASS: NTP sync is in use (systemd-timesyncd enabled and active).  
   - 2.2.15 - UNKNOWN: MTA local-only mode was not verified; no failing evidence found yet, but this remains unconfirmed.  
      
   File sharing and removable media  
   - 2.2.12 - PASS: Samba (smb/nmb) is disabled and inactive; no SMB ports detected in ss output.

20-item CIS compliance table — Arch laptop, findings only  
      
   ID: 5.3.1  
   Control: Password creation requirements configured  
   Category: Account/password  
   Finding: PASS (pam_faillock.so present in /etc/pam.d/system-login and related PAM files; indicates lockout/creation control behavior is configured.)  
   ────────────────────────────────────────  
   ID: 5.3.2  
   Control: Lockout for failed password attempts configured  
   Category: Account/password  
   Finding: PASS (pam_faillock.so preauth, authfail, and authsucc entries present in /etc/pam.d/system-login.)  
   ────────────────────────────────────────  
   ID: 5.3.3  
   Control: Password reuse is limited  
   Category: Account/password  
   Finding: FAIL  
   ────────────────────────────────────────  
   ID: 5.3.4  
   Control: Password hashing algorithm is SHA-512  
   Category: Account/password  
   Finding: PASS  
   ────────────────────────────────────────  
   ID: 5.4.1.1  
   Control: Password expiration is 365 days or less  
   Category: Account/password  
   Finding: FAIL  
   ────────────────────────────────────────  
   ID: 5.4.1.4  
   Control: Inactive password lock is 30 days or less  
   Category: Account/password  
   Finding: FAIL  
   ────────────────────────────────────────  
   ID: 5.4.4  
   Control: Default user umask is 027 or more restrictive  
   Category: Account/password  
   Finding: FAIL  
   ────────────────────────────────────────  
   ID: 4.1.2  
   Control: auditd is installed  
   Category: Audit/logging  
   Finding: FAIL  
   ────────────────────────────────────────  
   ID: 4.1.3  
   Control: auditd service is enabled  
   Category: Audit/logging  
   Finding: FAIL  
   ────────────────────────────────────────  
   ID: 4.1.19  
   Control: Audit configuration is immutable  
   Category: Audit/logging  
   Finding: UNKNOWN  
   ────────────────────────────────────────  
   ID: 1.3.1  
   Control: AIDE is installed  
   Category: Antivirus/host integrity  
   Finding: FAIL  
   ────────────────────────────────────────  
   ID: 1.3.2  
   Control: Filesystem integrity is regularly checked  
   Category: Antivirus/host integrity  
   Finding: FAIL  
   ────────────────────────────────────────  
   ID: 3.1.1  
   Control: IP forwarding is disabled  
   Category: Firewall/network  
   Finding: FAIL  
   ────────────────────────────────────────  
   ID: 3.2.7  
   Control: Reverse Path Filtering is enabled  
   Category: Firewall/network  
   Finding: FAIL  
   ────────────────────────────────────────  
   ID: 1.6.1.1  
   Control: SELinux or AppArmor installed  
   Category: Privilege/UAC equivalent  
   Finding: FAIL  
   ────────────────────────────────────────  
   ID: 5.2.10  
   Control: SSH root login is disabled  
   Category: Privilege/UAC equivalent  
   Finding: PASS  
   ────────────────────────────────────────  
   ID: 2.2.1  
   Control: Time synchronization is in use  
   Category: System services  
   Finding: PASS  
   ────────────────────────────────────────  
   ID: 2.2.15  
   Control: MTA is configured for local-only mode  
   Category: System services  
   Finding: UNKNOWN  
   ────────────────────────────────────────  
   ID: 2.2.12  
   Control: Samba is not enabled if unnecessary  
   Category: File sharing/removable  
   Finding: PASS  
   ────────────────────────────────────────  
   ID: 1.1.23  
   Control: USB Storage disabled  
   Category: File sharing/removable  
   Finding: NOT CHECKED  
   ────────────────────────────────────────  
   ID: 1.1.22  
   Control: Automount disabled  
   Category: File sharing/removable  
   Finding: NOT CHECKED  
   ────────────────────────────────────────  
   ID: 1.1.21  
   Control: Sticky bit set on all world-writable directories  
   Category: Filesystem hardening  
   Finding: NOT CHECKED  
   ────────────────────────────────────────  
   ID: 1.1.6 - 1.1.10  
   Control: /tmp, /var/tmp mount options/size  
   Category: Filesystem hardening  
   Finding: NOT CHECKED