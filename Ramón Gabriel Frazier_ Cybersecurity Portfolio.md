# **Ramón Gabriel Frazier: Cybersecurity Portfolio**

## **SQL Portfolio: Security Incident Investigation**

### **Project Overview**

This project outlines a series of SQL queries executed to investigate potential security incidents involving unauthorized login attempts and to support routine security updates across employee machines. The goal was to demonstrate proficiency in using SQL to query a database, apply filters, and analyze data to identify security-related anomalies.

### **Query 1: Retrieve After-Hours Failed Login Attempts**

I discovered some potential security issues with the log\_in\_attempts database and employees' machines. These attempts occurred after working hours, which is what sparked my suspicion. I decided to query the log\_in\_attempts database to further investigate. I know the success column contains a value of 0 when a login attempt fails, so I used a value of FALSE in my query to identify failed login attempts.

**SQL Code:**

SELECT \*  
FROM log\_in\_attempts  
WHERE login\_time \> '18:00' AND success \= FALSE;

### **Query 2: Retrieve Login Attempts on Specific Dates**

The suspicious activity took place on 2022-05-09, so I queried the database for failed login attempts on this date or the day before.

**SQL Code:**

SELECT \*  
FROM log\_in\_attempts  
WHERE login\_date \= '2022-05-09' OR login\_date \= '2022-05-08';

### **Query 3: Retrieve Login Attempts Outside of Mexico**

After inputting the previous queries, I believed the login attempts occurred outside of Mexico.

**SQL Code:**

SELECT \*  
FROM log\_in\_attempts  
WHERE NOT country LIKE 'MEX%';

### **Query 4: Retrieve Employees in Marketing**

My team wants to perform security updates on specific employee machines in the Marketing department for all offices in the East building.

**SQL Code:**

SELECT \*  
FROM employees  
WHERE department \= 'Marketing' AND office LIKE 'East%';

### **Query 5: Retrieve Employees in Finance or Sales**

My team needs me to perform another security update on machines for employees in the Sales and Finance departments.

**SQL Code:**

SELECT \*  
FROM employees  
WHERE department \= 'Finance' OR department \= 'Sales';

### **Query 6: Retrieve All Employees Not in IT**

My team needs me to update employee machines in all departments except the Information Technology department because they already had this update.

**SQL Code:**

SELECT \*  
FROM employees  
WHERE NOT department \= 'Information Technology';

## **Vulnerability Assessment Report**

### **System Description**

The server's hardware includes a powerful CPU and 128GB of memory. It runs on the latest version of the Linux operating system and utilizes a MySQL database management system. The system is configured with a stable network connection using IPv4 addresses and communicates with other servers across the network. Security measures include Transport Layer Security (TLS) and Secure Sockets Layer (SSL) encrypted connections.

### **Scope**

This vulnerability assessment covers the current access controls of the system. The assessment was conducted over a three-month period, from June 2025 to August 2025\. The risk analysis was guided by the methodology outlined in NIST SP 800-30 Rev. 1\.

### **Risk Assessment**

The following table outlines the identified threats, their likelihood, severity, and overall risk score. A comprehensive approach was taken to evaluate potential threats to data storage and management by balancing the need for continuous business operations with security requirements.

| Threat Source | Threat Event | Likelihood | Severity | Risk |
| ----- | ----- | ----- | ----- | ----- |
| Hacker | Obtain sensitive information via exfiltration | 3 | 3 | 9 |
| Employee | Denial of Service (DoS) | 2 | 3 | 6 |
| Customer | Alter/Delete information | 1 | 3 | 3 |

### **Remediation Strategy**

To ensure that only authorized users can access the database server, comprehensive authentication and authorization controls will be implemented. This includes enforcing a strong password policy, using role-based access controls, and requiring multi-factor authentication to limit user privileges. All data in transit will be secured through TLS encryption, and IP allow-listing will be used to restrict connections to trusted corporate networks, preventing unauthorized access from the internet.

## **Risk Register: Financial Institution**

### **Executive Summary**

This risk register identifies and assesses key risks to the bank’s operational environment, assets, and financial integrity. The analysis considers potential threats, their likelihood, severity, and overall priority, providing a foundation for developing effective mitigation strategies.

### **Operational Environment**

The bank operates in a low-crime coastal area, managing 2,000 individual and 200 commercial accounts. Its workforce consists of 120 employees, with 100 on-premise and 20 working remotely. The bank's services are actively promoted through partnerships with a professional sports team and ten local businesses. All operations are subject to strict financial regulations that mandate the secure management of data and funds.

### **Risk Assessment**

The following table details the identified risks, their potential impact, and a corresponding risk score. This score is calculated by multiplying Likelihood (1-3) by Severity (1-3).

### **Risk Register Table**

| Asset | Risk | Description | Likelihood | Severity | Priority |
| ----- | ----- | ----- | ----- | ----- | ----- |
| Funds | Business Email Compromise | An employee is deceived into sharing confidential information, leading to the unauthorized transfer of funds or data. | 2 | 2 | 4 |
| Funds | Compromised User Database | Inadequate encryption or access controls lead to the exposure of sensitive customer data. | 2 | 3 | 6 |
| Financial Records | Financial Records Leak | An attacker gains unauthorized access to a publicly exposed database containing backed-up financial records. | 3 | 3 | 9 |
| Funds | Physical Theft | Unauthorized physical access to the bank's safe or vault results in the loss of funds. | 1 | 3 | 3 |
| Supplies | Supply Chain Disruption | Natural disasters cause a disruption in the delivery of essential supplies. | 1 | 2 | 2 |

### **Risk Scoring Rationale**

The likelihood and severity scores were determined based on the bank's unique operational environment:

* **Physical Theft (Likelihood: 1):** The low-crime coastal area significantly reduces the probability of a physical security breach.  
* **Business Email Compromise (Likelihood: 2):** The high number of employees, especially those working remotely and potentially using unsecured networks, increases the likelihood of a successful phishing or social engineering attack.  
* **Compromised User Database (Likelihood: 2):** Given the large customer base, the potential for a database compromise is moderately likely and could have a widespread impact.  
* **Financial Records Leak (Likelihood: 3):** The existence of a database server with backed-up data that is publicly accessible poses an immediate and high probability of a breach.  
* **Supply Chain Disruption (Likelihood: 1):** While the coastal location makes natural disasters possible, the frequency is low, making a disruption event unlikely.

### **Recommendations**

Based on this assessment, the highest-priority risks relate to digital data security. Immediate action should be taken to address the publicly exposed database and improve access controls across all systems to prevent data leaks and unauthorized access. Physical and supply chain risks are considered lower priority at this time.

## **Botium Toys: Scope, Goals, and Risk Assessment Report**

### **Scope and Goals of the Audit**

**Scope:** The scope of this audit is defined as the entire security program at Botium Toys. This includes their assets like employee equipment and devices, their internal network, and their systems. You will need to review the assets Botium Toys has and the controls and compliance practices they have in place.

**Goals:** Assess existing assets and complete the controls and compliance checklist to determine which controls and compliance best practices that need to be implemented to improve Botium Toys’ security posture.

### **Current Assets**

Assets managed by the IT Department include:

* On-premises equipment for in-office business needs  
* Employee equipment: end-user devices (desktops/laptops, smartphones), remote workstations, headsets, cables, keyboards, mice, docking stations, surveillance cameras, etc.  
* Storefront products available for retail sale on site and online; stored in the company’s adjoining warehouse  
* Management of systems, software, and services: accounting, telecommunication, database, security, ecommerce, and inventory management  
* Internet access  
* Internal network  
* Data retention and storage  
* Legacy system maintenance: end-of-life systems that require human monitoring

### **Risk Assessment**

**Risk Description:** Currently, there is inadequate management of assets. Additionally, Botium Toys does not have all of the proper controls in place and may not be fully compliant with U.S. and international regulations and standards.

**Control Best Practices:** The first of the five functions of the NIST CSF is Identify. Botium Toys will need to dedicate resources to identify assets so they can appropriately manage them. Additionally, they will need to classify existing assets and determine the impact of the loss of existing assets, including systems, on business continuity.

**Risk Score:** On a scale of 1 to 10, the risk score is 8, which is fairly high. This is due to a lack of controls and adherence to compliance best practices.

**Additional Comments:** The potential impact from the loss of an asset is rated as medium, because the IT department does not know which assets would be at risk. The risk to assets or fines from governing bodies is high because Botium Toys does not have all of the necessary controls in place and is not fully adhering to best practices related to compliance regulations that keep critical data private/secure. Review the following bullet points for specific details:

* Currently, all Botium Toys employees have access to internally stored data and may be able to access cardholder data and customers’ PII/SPII.  
* Encryption is not currently used to ensure confidentiality of customers’ credit card information that is accepted, processed, transmitted, and stored locally in the company’s internal database.  
* Access controls pertaining to least privilege and separation of duties have not been implemented.  
* The IT department has ensured availability and integrated controls to ensure data integrity.  
* The IT department has a firewall that blocks traffic based on an appropriately defined set of security rules.  
* Antivirus software is installed and monitored regularly by the IT department.  
* The IT department has not installed an intrusion detection system (IDS).  
* There are no disaster recovery plans currently in place, and the company does not have backups of critical data.  
* The IT department has established a plan to notify E.U. customers within 72 hours if there is a security breach. Additionally, privacy policies, procedures, and processes have been developed and are enforced among IT department members/other employees, to properly document and maintain data.  
* Although a password policy exists, its requirements are nominal and not in line with current minimum password complexity requirements (e.g., at least eight characters, a combination of letters and at least one number; special characters).  
* There is no centralized password management system that enforces the password policy’s minimum requirements, which sometimes affects productivity when employees/vendors submit a ticket to the IT department to recover or reset a password.  
* While legacy systems are monitored and maintained, there is no regular schedule in place for these tasks and intervention methods are unclear.  
* The store’s physical location, which includes Botium Toys’ main offices, store front, and warehouse of products, has sufficient locks, up-to-date closed-circuit television (CCTV) surveillance, as well as functioning fire detection and prevention systems.

### **Controls and Compliance Checklist**

#### **Controls Assessment Checklist**

| Control | Explanation | Does Botium Toys currently have this control in place? |
| ----- | ----- | ----- |
| Least Privilege | Currently, all employees have access to customer data; privileges need to be limited to reduce the risk of a breach. | No |
| Disaster recovery plans | There are no disaster recovery plans in place. These need to be implemented to ensure business continuity. | No |
| Password policies | Employee password requirements are minimal, which could allow a threat actor to more easily access secure data/other assets via employee work equipment/the internal network. | No |
| Separation of duties | Needs to be implemented to reduce the possibility of fraud/access to critical data, since the company CEO currently runs day-to-day operations and manages the payroll. | No |
| Firewall | The existing firewall blocks traffic based on an appropriately defined set of security rules. | Yes |
| Intrusion detection system (IDS) | The IT department needs an IDS in place to help identify possible intrusions by threat actors. | No |
| Backups | The IT department needs to have backups of critical data, in the case of a breach, to ensure business continuity. | No |
| Antivirus software | Antivirus software is installed and monitored regularly by the IT department. | Yes |
| Manual monitoring, maintenance, and intervention for legacy systems | The list of assets notes the use of legacy systems. The risk assessment indicates that these systems are monitored and maintained, but there is not a regular schedule in place for this task and procedures/ policies related to intervention are unclear, which could place these systems at risk of a breach. | No |
| Encryption | Encryption is not currently used; implementing it would provide greater confidentiality of sensitive information. | No |
| Password management system | There is no password management system currently in place; implementing this control would improve IT department/other employee productivity in the case of password issues. | No |
| Locks (offices, storefront, warehouse) | The store’s physical location, which includes the company’s main offices, store front, and warehouse of products, has sufficient locks. | Yes |
| Closed-circuit television (CCTV) surveillance | CCTV is installed/functioning at the store’s physical location. | Yes |
| Fire detection/prevention | Botium Toys’ physical location has a functioning fire detection and prevention system. | Yes |

#### **Compliance Checklist**

##### **Payment Card Industry Data Security Standard (PCI DSS)**

| Best practice | Explanation | Does Botium Toys currently adhere to this compliance best practice? |
| ----- | ----- | ----- |
| Only authorized users have access to customers’ credit card information. | Currently, all employees have access to the company’s internal data. | No |
| Credit card information is accepted, processed, transmitted, and stored internally, in a secure environment. | Credit card information is not encrypted and all employees currently have access to internal data, including customers’ credit card information. | No |
| Implement data encryption procedures to better secure credit card transaction touchpoints and data. | The company does not currently use encryption to better ensure the confidentiality of customers’ financial information. | No |
| Adopt secure password management policies. | Password policies are nominal and no password management system is currently in place. | No |

##### **General Data Protection Regulation (GDPR)**

| Best practice | Explanation | Does Botium Toys currently adhere to this compliance best practice? |
| ----- | ----- | ----- |
| E.U. customers’ data is kept private/secured. | The company does not currently use encryption to better ensure the confidentiality of customers’ financial information. | No |
| There is a plan in place to notify E.U. customers within 72 hours if their data is compromised/there is a breach. | There is a plan to notify E.U. customers within 72 hours of a data breach. | Yes |
| Ensure data is properly classified and inventoried. | Current assets have been inventoried/listed, but not classified. | No |
| Enforce privacy policies, procedures, and processes to properly document and maintain data. | Privacy policies, procedures, and processes have been developed and enforced among IT team members and other employees, as needed. | Yes |

##### **System and Organizations Controls (SOC type 1, SOC type 2\)**

| Best practice | Explanation | Does Botium Toys currently adhere to this compliance best practice? |
| ----- | ----- | ----- |
| User access policies are established. | Controls of Least Privilege and separation of duties are not currently in place; all employees have access to internally stored data. | No |
| Sensitive data (PII/SPII) is confidential/private. | Encryption is not currently used to better ensure the confidentiality of PII/SPII. | No |
| Data integrity ensures the data is consistent, complete, accurate, and has been validated. | Data integrity is in place. | Yes |
| Data is available to individuals authorized to access it. | While data is accessible to all employees, access authorization must be restricted to individuals who require it to perform their jobs. This is based on the security principle of least privilege, which minimizes an employee’s access to the information and systems necessary for their specific role. | No |

**Recommendations:** To enhance Botium Toys’ security posture and address compliance gaps, a comprehensive set of controls should be implemented. This effort begins with properly classifying all assets to identify specific protection requirements.

Key controls to be deployed include:

* **Access Control:** Applying the principle of least privilege, enforcing separation of duties, and implementing a strong password policy to ensure only authorized users can access sensitive information.  
* **Data Protection:** Securing data with encryption and a centralized password management system.  
* **System Monitoring:** Deploying an intrusion detection system (IDS) for ongoing threat detection.  
* **Resilience & Management:** Establishing disaster recovery plans and ensuring continuous management of legacy systems.

## **Incident Final Report**

### **Executive Summary**

At 7:20 p.m. PT on December 28, 2022, a security incident resulted in unauthorized access to the Personally Identifiable Information (PII) and financial data of approximately 50,000 customers. The estimated financial impact of the breach is $100,000. A comprehensive investigation has been conducted, and the incident has been successfully remediated and closed.

### **Timeline**

* **December 22, 2022, at 3:13 p.m. PT:** A threat actor attempted to extort the organization via email, claiming to have exfiltrated customer data and demanding a $25,000 cryptocurrency payment. The initial email was not reported and was subsequently deleted by the employee who received it.  
* **December 28, 2022:** A second email was received from the same sender. This communication included a sample of the compromised data and an increased ransom demand of $50,000. Upon receipt, the employee promptly reported the incident to the security team, initiating a formal investigation. The security team immediately commenced forensic analysis to determine the method of data exfiltration and the full scope of the breach.

### **Investigation**

Upon receiving the alert, the security team initiated an immediate on-site investigation. The root cause was identified as a forced browsing vulnerability in the e-commerce web application. The attacker exploited this flaw by manipulating the order number parameter in the URL of a purchase confirmation page, allowing unauthorized access to sensitive customer data. A subsequent review of web application access logs corroborated this finding, confirming that the attacker had accessed and exfiltrated data from thousands of purchase confirmation pages.

### **Response and Remediation**

Following the security incident, the organization coordinated with its public relations department to formally disclose the data breach to affected customers. As a gesture of goodwill and part of its mitigation efforts, the organization offered complimentary identity protection services to all impacted individuals. A post-incident review of the web server logs immediately clarified the attack vector, revealing a single log source generating an exceptionally high volume of sequentially listed customer order requests.

### **Recommendations**

To prevent future recurrences, the following actions are being taken:

* Perform routine vulnerability scans and penetration testing.  
* Implement the following access control mechanisms:  
  * Implement allowlisting to allow access to a specified set of URLs and automatically block all requests outside of this URL range.  
  * Ensure that only authenticated users are authorized to access content.

## **Network Interruption Report**

### **Section 1: Identify the Type of Attack**

The connection timeout experienced by users appears to be the result of a **Denial-of-Service (DoS) attack**, specifically a SYN flood. Server logs confirmed that the web server was overwhelmed with an excessive volume of SYN packet requests, which is the defining characteristic of this type of attack and directly led to the service outage.

### **Section 2: Explanation of Website Malfunction**

Normal website connections are established through the **TCP three-way handshake**. This process begins with a client sending a SYN packet to the server. The server then responds with a SYN-ACK packet and allocates resources to prepare for the connection. The handshake is completed when the client sends a final ACK packet.

During a SYN flood attack, a malicious actor sends a large volume of SYN packets to the server but intentionally never sends the final ACK packet. The server's connection queue quickly becomes overwhelmed with a backlog of half-open connections. As the queue fills up, the server can no longer accept new, legitimate connections from visitors, causing connection timeout errors in the logs and rendering the website unresponsive to its users.

## **Network Traffic Analysis**

### **Part 1: Summary of DNS and ICMP Traffic Log**

The network analysis of DNS and ICMP traffic logs revealed a critical issue: UDP port 53 was unreachable. This was identified through the ICMP echo reply, which returned a "Port Unreachable" error message. Since UDP port 53 is specifically used for the DNS service, the most probable cause of this incident is that no service was listening on the DNS port at the time the queries were made.

### **Part 2: Analysis and Cause of Incident**

**Time incident occurred:** 1:24 p.m., 32.192571 seconds.

**How the IT team became aware of the incident:** The incident was initially reported by customers who were experiencing network issues.

**Analysis of the data and potential causes:** The logs indicate a failure in the DNS service, which would prevent clients from resolving domain names. There are two primary potential causes for this incident:

* **A Deliberate Attack:** It is possible that a threat actor disabled the DNS server, potentially using a Denial-of-Service (DoS) attack.  
* **Configuration Error:** Alternatively, the issue could have stemmed from a human error, such as an IT team member making a configuration change to a firewall that inadvertently blocked traffic to port 53\.

## **Data Leak Analysis**

### **Incident Summary**

A sales manager shared access to a folder of internal-only documents with their team. The folder contained confidential files for an unannounced product, including customer analytics and promotional materials. The manager failed to revoke access after the meeting.

During a subsequent video call with a business partner, a sales team member mistakenly shared a link to the entire internal folder instead of the intended promotional materials. Unaware of the error, the business partner then posted the link on their company's social media, leading to a public data leak.

### **Analysis**

#### **Control:**

Least Privilege

#### **Issue(s):**

The principle of least privilege was not applied. Access to the internal folder was not limited to a "need-to-know" basis. The sales team, and by extension the business partner, had access to confidential information beyond the scope of their role.

#### **Review:**

This incident highlights a clear violation of **NIST SP 800-53: AC-6**, which addresses the importance of protecting against data leaks by applying the principle of least privilege. Granting access for a single meeting and failing to revoke it immediately afterward created an unnecessary security vulnerability.

### **Recommendation(s)**

* **Implement Automated Access Control:** Automatically revoke access to information after a specific period of time (e.g., after 24 hours).  
* **Enforce Least Privilege:** Provide users with only the minimal access and authorization required to complete a specific task or function.

### **Justification**

By restricting access to only the specific promotional materials needed for a task, the risk of a data leak is significantly reduced. Regularly performing access audits and enforcing strong password policies can also help prevent potential data leaks.

## **PASTA Worksheet**

## **I. Define Business and Security Objectives**

The application's primary function is to process transactions for a sneaker company. Key objectives include:

* Ensuring a seamless and secure user sign-up and login process.  
* Implementing user-to-user message encryption, such as using AES, for the protection of sensitive data.  
* Maintaining strict compliance with Payment Card Industry Data Security Standard (PCI DSS).

## **II. Define the Technical Scope**

The application utilizes a multi-layered security architecture with the following technologies:

* **Application Programming Interface (API):** The API ensures secure and seamless communication between various software components, including the seller and shopper interfaces.  
* **Public Key Infrastructure (PKI):** A robust PKI will be established to provide encryption for sensitive data both in transit and at rest, utilizing both symmetric and asymmetric encryption to protect Personally Identifiable Information (PII) and Sensitive Personally Identifiable Information (SPII).  
* **SHA-256 Hashing:** The industry-standard SHA-256 hashing function will be used to protect critical information like passwords and credit card numbers. This creates a unique, irreversible 256-bit digest that safeguards data even if the database is compromised.  
* **SQL Database:** A relational SQL database is the optimal choice for reliable and scalable data storage due to the structured nature of the data (e.g., specific fields for sneaker models, sizes, and user information).

## **III. Threat Analysis**

The following threats pose a significant risk to the information handled by the application:

1. **Injection:** A threat actor could exploit a vulnerability to inject malicious code (e.g., SQL injection) that compromises the database.  
2. **Session Hijacking:** An attacker could steal a legitimate user's session token to gain unauthorized access to their account and sensitive information.

## **IV. Vulnerability Analysis**

The following vulnerabilities could be exploited by a threat actor:

1. **Lack of Prepared Statements:** If the application does not use prepared statements, it is vulnerable to SQL injection attacks, allowing an attacker to manipulate database queries.  
2. **Mobile Code Flaw:** Flaws in the application's client-side code could allow an attacker to bypass security controls or gain unauthorized access to data.

## **V. Risk Analysis and Impact**

### **Security Controls**

To mitigate the identified risks, the following security controls will be implemented:

1. **Secure API Design:** Implementing a secure API with proper authentication and input validation will prevent malicious injection attacks.  
2. **Strong Password Policies:** Enforcing a strong password policy, including rules for complexity, rotation frequency, and disallowing password recycling, will protect user accounts.  
3. **SHA-256 Hashing:** Using SHA-256 for password hashing will ensure that even if the database is compromised, passwords remain secure and unreadable.  
4. **Principle of Least Privilege:** Limiting user and system access to only the data and resources absolutely necessary to perform a given task will reduce the attack surface and potential damage from a breach.

## **Incident Handler's Journal Log**

**Date:** 07/25/2025

**Entry Number:** 001

**Description:** A security incident was identified and documented, involving a ransomware attack that led to the encryption of critical files and a significant disruption of business operations.

**5 W's**

* **Who:** A malicious threat actor specializing in cyberattacks against the healthcare and transportation industries.  
* **What:** The threat actor executed a ransomware attack, which encrypted critical files, including patient data.  
* **When:** The incident was discovered on Tuesday at 9:00 a.m.  
* **Where:** The attack originated and spread across multiple company computers.  
* **Why:** The motive appears to be financial, consistent with a known hacking group that targets specific sectors for extortion.

**Additional Notes:** Initial access was gained via a successful phishing campaign. The attack chain began when an employee downloaded a malicious email attachment, which installed malware on their computer. The threat actor then used this foothold to deploy their ransomware payload, which encrypted critical files and caused a major business disruption.

