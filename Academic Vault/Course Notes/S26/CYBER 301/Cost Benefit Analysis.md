Identify EF, ARO, and compute SLE and ALE for each scenario. Evaluate the cost benefit of the proposed controls to justify their implementation.

Exposure Factor (EF) = Percent of Asset Affected
Annual Rate of Occurrence (ARO) = How often the incident occurs annually
Single Loss Expectancy (SLE) = Asset Value * Exposure Factor
Annual Loss Expectancy (ALE) = Single Loss Expectancy * Annual Rate of Occurrence

**Scenario A: Company Laptops**

A mid-sized marketing firm has noticed an uptick in laptop theft. In the last year, five laptops disappeared from employee desks. Each laptop costs approximately $2,000, and recovery and re-imaging adds roughly another $2,000 per incident. An external consultant has proposed a laptop locking and monitoring system for $1,500 per year, which is claimed to reduce the risk from five incidents a year down to roughly one.

**Scenario B: Phishing and Employee Training**

A financial services company has been struggling with phishing attacks, costing roughly $25,000 due to recovery efforts and lost productivity per successful attack. Currently, three attacks occur every year. An employee training program costing $10,000 per year is proposed, expected to reduce incidents to roughly one every two years.

**Scenario C: Ransomware Incident and New Detection Tools**

A regional law firm suffered a ransomware attack recently, costing approximately $100,000. Currently, incidents occur roughly once per year. A cybersecurity vendor has offered a detection service for $18,000 per year that may reduce incidents to roughly one every four years.

**Scenario D: Insider Threat Monitoring**

A medical research company maintains a database worth roughly $250,000. An insider breach can result in data exposure and penalties estimated at roughly 25% of the database value. Currently, the risk occurs roughly once every two years. An employee monitoring service costing $15,000 per year is expected to reduce risk to roughly one breach every ten years.

**Scenario E: DoS Attack Mitigation**

An online retailer experiences denial-of-service attacks that cost roughly $15,000 per hour, with incidents lasting about an hour. Currently, about four incidents occur every year. An automated DDoS mitigation service costing $25,000 per year is proposed, expected to reduce incidents to roughly one per year.

**Scenario F: Fire Suppression System**

A manufacturing plant has equipment valued at roughly $1,000,000, with a potential loss of roughly half its value in case of an electrical fire. The risk occurs roughly once every hundred years. A state-of-the-art fire suppression system costing $10,000 per year can reduce the risk tenfold.

**Scenario G: USB Malware Risk**

A small engineering firm experiences roughly one malware infection per month caused by unauthorized USB devices. Each incident costs roughly $5,000 in recovery and downtime. An endpoint security solution costing $3,000 per year can reduce incidents to roughly three per year.

**Scenario H: Securing a Web App Against SQL Injection**

A SaaS company operates a customer portal that, when compromised by SQL injection attacks, results in roughly $30,000 in recovery, legal, and reputational costs. Currently, about two incidents occur every year. An application firewall costing $20,000 per year is proposed, expected to reduce incidents to roughly one every four years.

# Answers

**Scenario A: Company Laptops**

A mid-sized marketing firm has noticed an uptick in laptop theft. In the last year, five laptops disappeared from employee desks. Each laptop costs approximately $2,000, and recovery and re-imaging adds roughly another $2,000 per incident. An external consultant has proposed a laptop locking and monitoring system for $1,500 per year, which is claimed to reduce the risk from five incidents a year down to roughly one.

- **EF:** 100% (The entire asset value and associated recovery costs are realized upon theft) 
- **ARO:** 5 (Current) | 1 (Proposed)
- **SLE:** $4,000 ($2,000 laptop + $2,000 recovery)
- **ALE:** $20,000 (Current: $4,000 * 5) | $4,000 (Proposed: $4,000 * 1)
- **Cost Benefit Analysis:** The current ALE is $20,000. With the control, the new ALE is $4,000. This creates a risk reduction of $16,000. Subtracting the $1,500 control cost yields a net benefit of $14,500 per year.
    
**Scenario B: Phishing and Employee Training**

A financial services company has been struggling with phishing attacks, costing roughly $25,000 due to recovery efforts and lost productivity per successful attack. Currently, three attacks occur every year. An employee training program costing $10,000 per year is proposed, expected to reduce incidents to roughly one every two years.

- **EF:** 100% (The full estimated cost of the incident is realized per attack)
- **ARO:** 3 (Current) | 0.5 (Proposed: 1 incident / 2 years)
- **SLE:** $25,000
- **ALE:** $75,000 (Current: $25,000 * 3) | $12,500 (Proposed: $25,000 * 0.5)
- **Cost Benefit Analysis:** The current ALE is $75,000. The proposed control reduces the ALE to $12,500, a savings of $62,500. Subtracting the $10,000 control cost yields a net benefit of $52,500 per year.

**Scenario C: Ransomware Incident and New Detection Tools**

A regional law firm suffered a ransomware attack recently, costing approximately $100,000. Currently, incidents occur roughly once per year. A cybersecurity vendor has offered a detection service for $18,000 per year that may reduce incidents to roughly one every four years.

- **EF:** 100% (The full cost of the ransomware incident is realized) 
- **ARO:** 1 (Current) | 0.25 (Proposed: 1 incident / 4 years)
- **SLE:** $100,000
- **ALE:** $100,000 (Current: $100,000 * 1) | $25,000 (Proposed: $100,000 * 0.25)
- **Cost Benefit Analysis:** The current ALE is $100,000. The proposed control reduces the ALE to $25,000, creating $75,000 in risk reduction. Subtracting the $18,000 control cost yields a net benefit of $57,000 per year.

**Scenario D: Insider Threat Monitoring**

A medical research company maintains a database worth roughly $250,000. An insider breach can result in data exposure and penalties estimated at roughly 25% of the database value. Currently, the risk occurs roughly once every two years. An employee monitoring service costing $15,000 per year is expected to reduce risk to roughly one breach every ten years.

- **EF:** 25%
- **ARO:** 0.5 (Current: 1 incident / 2 years) | 0.1 (Proposed: 1 incident / 10 years)
- **SLE:** $62,500 ($250,000 * 0.25)
- **ALE:** $31,250 (Current: $62,500 * 0.5) | $6,250 (Proposed: $62,500 * 0.1)
- **Cost Benefit Analysis:** The current ALE is $31,250. The control reduces the ALE to $6,250, saving $25,000. Subtracting the $15,000 control cost yields a net benefit of $10,000 per year.

**Scenario E: DoS Attack Mitigation**

An online retailer experiences denial-of-service attacks that cost roughly $15,000 per hour, with incidents lasting about an hour. Currently, about four incidents occur every year. An automated DDoS mitigation service costing $25,000 per year is proposed, expected to reduce incidents to roughly one per year.

- **EF:** 100% (of the 1-hour incident cost)
- **ARO:** 4 (Current) | 1 (Proposed)
- **SLE:** $15,000
- **ALE:** $60,000 (Current: $15,000 * 4) | $15,000 (Proposed: $15,000 * 1)
- **Cost Benefit Analysis:** The current ALE is $60,000. The control lowers it to $15,000, for a savings of $45,000. Subtracting the $25,000 control cost yields a net benefit of $20,000 per year.

**Scenario F: Fire Suppression System**

A manufacturing plant has equipment valued at roughly $1,000,000, with a potential loss of roughly half its value in case of an electrical fire. The risk occurs roughly once every hundred years. A state-of-the-art fire suppression system costing $10,000 per year can reduce the risk tenfold.

- **EF:** 50%
- **ARO:** 0.01 (Current: 1 incident / 100 years) | 0.001 (Proposed: tenfold reduction, or 1 incident / 1,000 years)
- **SLE:** $500,000 ($1,000,000 * 0.50)
- **ALE:** $5,000 (Current: $500,000 * 0.01) | $500 (Proposed: $500,000 * 0.001)
- **Cost Benefit Analysis:** The current ALE is $5,000. The control lowers the ALE to $500, creating $4,500 in risk reduction. However, the control costs $10,000 per year. Subtracting the cost gives a net loss of $5,500 per year.

**Scenario G: USB Malware Risk**

A small engineering firm experiences roughly one malware infection per month caused by unauthorized USB devices. Each incident costs roughly $5,000 in recovery and downtime. An endpoint security solution costing $3,000 per year can reduce incidents to roughly three per year.

- **EF:** 100% (The full $5,000 loss is realized per event)
- **ARO:** 12 (Current: 1 incident per month) | 3 (Proposed)
- **SLE:** $5,000
- **ALE:** $60,000 (Current: $5,000 * 12) | $15,000 (Proposed: $5,000 * 3)
- **Cost Benefit Analysis:** The current ALE is $60,000. The control lowers it to $15,000, yielding $45,000 in risk reduction. Subtracting the $3,000 control cost leaves a net benefit of $42,000 per year.

**Scenario H: Securing a Web App Against SQL Injection**

A SaaS company operates a customer portal that, when compromised by SQL injection attacks, results in roughly $30,000 in recovery, legal, and reputational costs. Currently, about two incidents occur every year. An application firewall costing $20,000 per year is proposed, expected to reduce incidents to roughly one every four years.

- **EF:** 100% (The full estimated loss footprint is realized per event)
- **ARO:** 2 (Current) | 0.25 (Proposed: 1 incident / 4 years)
- **SLE:** $30,000
- **ALE:** $60,000 (Current: $30,000 * 2) | $7,500 (Proposed: $30,000 * 0.25)
- **Cost Benefit Analysis:** The current ALE is $60,000. The control lowers it to $7,500, giving $52,500 in risk reduction. Subtracting the $20,000 control cost leaves a net benefit of $32,500 per year.