## Unknown Date
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

6. Using your strategy and classifications, create a data classification document and upload your document here. (Just use AI to draft a policy based on your answers to questions 1-5.)

**Document Title:** BYU-Idaho Data Classification and Handling Policy

**Version:** 1.0

**Effective Date:** [Date]

#### 1. Purpose and Scope

The purpose of this policy is to establish a framework for classifying data collected and maintained by BYU-Idaho. This ensures that data is protected with appropriate security controls in compliance with institutional policies and regulatory requirements (e.g., FERPA, HIPAA, PCI DSS). This policy applies to all university employees, faculty, contractors, and student workers who access university information systems.

#### 2. Roles and Responsibilities

- **Data Owners:** Senior university officials or department heads (e.g., University Registrar, Director of Student Health Center, Head of Financial Aid) responsible for a specific domain of data. They determine who is authorized to access the data based on job roles.
    
- **Data Custodians:** Information Technology (IT) personnel responsible for the safe custody, transport, storage, and technical provisioning of access to the data, as directed by the Data Owners.
    
- **Data Users:** Authorized employees, faculty, or student workers who access data to perform their defined job duties.
    
- **Information Security (InfoSec):** Responsible for monitoring access, defining security controls, managing the SIEM, and auditing compliance with this policy.
    

#### 3. Data Classification Tiers & Inventory

All university data must be classified into one of the following four tiers.

|**Classification**|**Definition**|**Examples (BYU-I Context)**|
|---|---|---|
|**1. Public**|Information that is freely available to the public and poses no risk if disclosed.|General university directory, institutional research (public reports), course catalogs, GIS campus maps.|
|**2. Internal Use Only**|Information intended for university employees and students. Unauthorized disclosure would cause minimal risk.|Internal memos, non-sensitive departmental data, general digital usage metrics, standard employee directories.|
|**3. Confidential**|Sensitive information protected by privacy laws or institutional policy. Disclosure could cause moderate to high harm.|Educational records (FERPA), PII (home addresses, birth dates, demographic info), ecclesiastical records.|
|**4. Restricted**|Highly sensitive data. Unauthorized disclosure would cause severe financial, legal, or reputational damage.|Financial data, SSNs, Health Records (HIPAA), tax documents (1098-T), insurance policy details, payment card info.|

#### 4. Access Control Strategy

- **Role-Based Access Control (RBAC):** Access to Confidential and Restricted data is granted strictly based on the user’s job function and the Principle of Least Privilege. For example, academic advising staff will have access to grad planner records, while Human Resources staff will not.
    
- **Access Provisioning:** Access must be formally requested by the user's supervisor and explicitly approved by the relevant Data Owner. IT will execute the provisioning.
    
- **Access Revocation:** Upon termination or transfer of an employee, Data Owners and HR must immediately notify IT to revoke all system access.
    

#### 5. Data Security and Auditing

- **Logging:** All systems housing Confidential or Restricted data must log user access, including timestamps, user IDs, and the specific files accessed.
    
- **Monitoring:** Information Security will utilize a Security Information and Event Management (SIEM) system to monitor access logs. Automated alerts will be configured to flag anomalous activities, such as bulk downloads or access during off-hours.
    
- **Auditing:** InfoSec will conduct periodic audits of access logs and current user permissions to ensure alignment with the Principle of Least Privilege.
    

#### 6. Enforcement

Violations of this policy, whether intentional or accidental, may result in disciplinary action up to and including termination of employment or academic dismissal, as well as potential civil or criminal penalties.

## May 27 Class
**Test Prep Q&A**
- Answer the multiple-choice questions first, save the problem based questions for the end.
	- Skip questions you don't know the answers to, then come back to them afterward. Give yourself time to relax and get your brain back into gear (will probably happen around question 8-10)
- Go to the Computer Based Test counter at the testing center (don't wait in the regular testing line), get there 10-15 mins early.
- Don't leave right away. Testing Center will print out a paper with your score on it, and they will give it to you. Upload a photo of that paper to Canvas.
- If you don't pass, take note of which sections you missed questions on (it will say on your results paper?), study hard on those and keep up on others, then retake the exam after two or three weeks.
- Use all of your resources to prepare (AI exams, LinkedIn Learning, Professor Messer videos, Oreilly videos and quizzes, etc.)
**Wireless**
- Wireless is generated by sending an electrical signal to an antenna, which sends it out as a radio wave at the frequency the antenna is tuned to.
- Frequencies go from low to high. Low frequencies penetrate well and go far, high frequencies do not.
- Certain combinations of metal/paint/other material can create a faraday cage, which keeps signals boxed into the cage
- FCC regulates frequencies
	- [US Frequency Allocations chart](https://www.ntia.gov/sites/default/files/2025-09/ntia-us-frequency-allocations.pdf)
- Wifi classifications:
![[IMG_4308.jpeg]]
- Wifi Security Standards:
![[IMG_4309.jpeg]]
- WPA3's SAE (Simultaneous Authentication of Equals) prevents keys from being reused
- Pre-Shared Keys (802.1x Personal setup, uses a password for every device to log into the network)
- 802.1x Enterprise (has a RADIUS server that users sign into with their unique user names and passwords to authenticate and connect to the network) (can be used on a home setup if you really want to)
## May 29 Class
**4.2 Topic Review**
- It's impossible to say how important it is to have an inventory of your systems, hardware, software, and other assets on the network. Make diagrams, lists, maps, etc. so you can keep track of things, scan for vulnerabilities, etc.
- Decommissioning
	- To truly decommission a device, you practically have to destroy it. For magnetic media, use sanitization programs to overwrite all of the data numerous times, or drill a hole in it, etc.
**Using AI to Make Life Easier as a Cybersecurity Specialist**
- n8n (AI orchestration/automation tool)
	- Useful for AI integration in your automated workflows
	- For every operating system, there are "guidelines" for how to integrate and keep your environment safe
		- Published guidelines are called STIGs (NIST has them)
	- The automation speeds up our ability to respond to incidents. 
		- For example, have an AI run a scan every 5 minutes to detect unknown connections to the network, pull the source IPs from those connections, take them to the firewall, and block those IPs at the firewall.
	- NetworkChuck has good YouTube videos on setting up and using n8n.
- Claude Code is also good.
**Software Inventory Lab**
- Don't inventory more than 100 items.
- Follow the lab document and submit it by the deadline.
- Use AI for as much as possible (it is especially useful for finding license info, whether the software is outdated, etc
## June 1 Class
**4.3 Topic Review**
- OSINT
	- osintframework.com
- Dark Web
	- Tor Browser
		- Creates anonymity by routing traffic through a number of nodes to obscure user IP
	- NetworkChuck has videos explaining what the dark web is and how to access it
	- No reason to really use the dark web unless you're conducting research (e.g., is my company's data being sold there?)
- National Vulnerability Database 
	- [https://nvd.nist.gov/vuln/search](https://nvd.nist.gov/vuln/search)
- CVSS Score Calculation
	-  https://www.first.org/cvss/v3.1/specification-document
	- Base Metric Group
		- Exploitability Metrics
			- Attack Vector
				- Network (N)
				- Adjacent (A)
				- Local (L)
				- Physical (P)
			- Attack Complexity
				- Low (L)
				- High (H)
			- Privileges Required
				- None (N)
				- Low (L)
				- High (H)
			- User Interaction
				- None (N)
				- Required (R)
		- Scope 
			- Unchanged (U)
			- Changed (C)
		- Impact Metrics
			- Confidentiality
				- High (H)
				- Low (L)
				- None (N)
			- Integrity
				- High (H)
				- Low (L)
				- None (N)
			- Availability
				- High (H)
				- Low (L)
				- None (N)
	- Temporal Metric Group
	- Environmental Metric Group
**CVSS Lab**
- Address: 