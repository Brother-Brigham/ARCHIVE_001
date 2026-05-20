- Phishing is much easier than hacking; why break in the code when you can just get someone to give you credentials?
- Bug bounty programs are a good way to incentivize exploit reporting. Payouts on an annual basis are pretty big aross the industry.
- IEEE mentioned, the big organization that defines things like WiFi protocols
- SMTP protocol (email) - no security because it's a legacy protocol from the '80s that doesn't have any built-in sender verification; we've had to band-aid security solutions on top of the protocol to try to help clarify the legitimacy of emails.
	- MX Lookup is a good tool for finding DNS entries
		- The spf record reveals which IP addresses are legitimate IP addresses to receive emails from. 
- https://phishingquiz.withgoogle.com/ to see how good we are at detecting phishing emails
- Lots of the famous hackers go to jail, get out, and then make tons of money at big companies because they were famous and talented--Kevin Mitnick & others
- "Phishing" comes from "Phone fishing" Origins of phishing in "phreaking"--hacking phone systems.
- Homoglyph Attack Generator - irongeek.com - can use characters that look identical but are technically different in order to impersonate legitimate web URLs
- NMAP Lab (in the Sec+ exam, you may get a question about what NMAP is) - due at midnight tonight.
	- Just run a scan on scanme.nmap.org
	- Nmap is preinstalled on Kali, so you don't have to install it separately if you still have your VM. Otherwise, you can install it for the lab.
- No class on Monday, but the Topic and a lab assignment will be due. Prof has a jury summons that he couldn't get out of; judge wants him to come in and demonstrate a hardship (can't get classes covered by other faculty)

## May 20 Class
- Review of 3.2 Topics
	- 802.1x (an authentication protocol that determines whether a user should be allowed on the network or not)
	- Proxy servers (those can reduce risk of phishing by allow-listing/whitelisting necessary sites that they need to go to, which the proxy server will retrieve for the user if whitelisted; users that require more access can be given broad access with the exception of blacklisted sites to provide security)
- Arctic Wolf review - GRC (Governance, Risk, Compliance)
	- GRC is more managerial/policy focused
	- 3.3 Topics are GRC-related
- Data Collection Assignment done with table groups - my answers for assignment:
1.  Identify the types of data BYU-Idaho collects.
Financial data, PII (SSN, home address, dorm address, legal names, photos, birth dates, nationality, ethnicity, marital status), educational records, health records (Student Health Center), tax documents (1099-T(?)) related to tuition and grants, ecclesiastical records, insurance information (policy info if privately insured or using school's student policy), digital usage, institutional research, GIS info, internal data, employee records.

2. Create classifications for these types of data.
Public, internal use only, confidential, and restricted.

3. Identify who should be the data owners, data custodians, and data users for the categories of data.
Health managed by Student Health Center; registration/academic records managed by Registrar's Office; departmental data managed by department; IT and InfoSec serves as custodians?

4. Identify who should have access to these categories of data and who should decide who has access.
Access should be determined by relevance to job tasks (Advising should have access to grad planner records but HR should not, etc.); IT/InfoSec should have ability to determine access based on access requests from data owners to authorize users (e.g., Head of Financial Aid should be able to request that new hire be given access to job-relevant Financial Aid data or that former employee access be revoked).

5. Come up with a strategy for ensuring the data isn't accessed by those not authorized and how this data will be logged.
Follow principles of least privilege; log user access on files, and audit access logs occasionally. Use a SIEM to flag access at odd hours.

6. Using your strategy and classifications, create a data classification document and upload your document here. 

"Even though this is a team assignment, each student needs to submit their own final report."