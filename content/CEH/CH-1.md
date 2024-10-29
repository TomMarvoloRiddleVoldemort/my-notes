# Frameworks
---
---
## MITRE ATT&CK
---
The **MITRE ATT&CK® framework** (Adversarial Tactics, Techniques, and Common Knowledge) is a comprehensive knowledge base of adversary tactics and techniques based on real-world observations. Developed by MITRE, it’s widely used in cybersecurity to understand and defend against cyber threats by providing a structured way to analyze and classify various attack methods.

### Key Components of the MITRE ATT&CK Framework

1. **Tactics**: These represent the goals or objectives that an adversary aims to achieve during an attack. They are high-level categorizations of what an attacker is trying to accomplish. For example:
   - **Initial Access**: Gaining access to a network.
   - **Execution**: Running malicious code.
   - **Persistence**: Maintaining access to the system.

2. **Techniques**: These are specific methods or ways adversaries use to achieve their tactical objectives. Techniques are detailed and describe how an attacker might execute a tactic. For instance:
   - **Phishing** (under Initial Access): A technique for tricking individuals into revealing credentials or executing malicious attachments.
   - **Command and Scripting Interpreter** (under Execution): Using command-line interfaces or scripts to execute commands.

3. **Sub-techniques**: These provide further granularity by breaking down techniques into more specific methods or variations. For example, the technique **"Command and Scripting Interpreter"** might include sub-techniques like **"PowerShell"** or **"Scripting"**.

4. **Procedures**: These are real-world examples of how techniques are used by adversaries. Procedures illustrate how specific techniques have been implemented in actual attacks.

5. **Mitigations**: These are recommendations for defending against techniques and reducing the likelihood or impact of an attack. They are practical measures that organizations can implement to bolster their security posture.

6. **Detections**: This aspect provides guidance on how to detect when a technique is being used. It includes methods and tools for monitoring and identifying malicious activity.

### Framework Structure

The MITRE ATT&CK framework is structured into matrices, with each matrix corresponding to different environments, such as:

- **Enterprise ATT&CK**: Focuses on techniques used in enterprise environments.
- **Mobile ATT&CK**: Addresses tactics and techniques relevant to mobile devices.
- **Cloud ATT&CK**: Covers techniques specific to cloud environments.

### Using the MITRE ATT&CK Framework

1. **Threat Hunting**: Analysts use the framework to develop hypotheses and hunt for indicators of compromise or anomalous behavior that aligns with known techniques.

2. **Incident Response**: Helps responders understand the possible tactics and techniques involved in an ongoing attack, enabling more effective containment and remediation.

3. **Red Teaming**: Red teams use the framework to simulate realistic attack scenarios and test the defensive measures of an organization.

4. **Blue Teaming**: Blue teams use ATT&CK to identify gaps in their defenses, refine security monitoring, and improve their incident response strategies.

5. **Security Operations**: Integrates with Security Information and Event Management (SIEM) systems to provide context for alerts and improve overall security visibility.


![[Pasted image 20240912095334.png]]
![[Pasted image 20240912095411.png]]

### Example of ATT&CK in Practice

Imagine a security team detects unusual network traffic. Using the MITRE ATT&CK framework, they might identify this traffic as related to a specific technique, such as **"Data Staged"**, where an attacker prepares exfiltrated data for transfer. By understanding the associated tactics and techniques, they can investigate further and implement appropriate mitigations.

Overall, the MITRE ATT&CK framework is a valuable tool for understanding the methods used by adversaries and enhancing an organization's ability to detect, respond to, and defend against cyber threats.



## NIST Framework 2.0
---
The NIST Framework 2.0, formally known as the "NIST Cybersecurity Framework (CSF) 2.0," is an updated version of the original NIST Cybersecurity Framework. Released by the National Institute of Standards and Technology (NIST), this framework provides a structured approach to managing and reducing cybersecurity risk. The 2.0 version, which was finalized in 2023, builds upon the original framework with enhancements and refinements based on feedback and evolving cybersecurity practices.

Here’s a high-level overview of the NIST Cybersecurity Framework 2.0:

### Key Components:

1. **Core Functions**: The framework is organized into five core functions:
   - **Identify**: Understand and manage cybersecurity risks to systems, people, assets, data, and capabilities.
   - **Protect**: Implement safeguards to ensure delivery of critical infrastructure services.
   - **Detect**: Develop and implement appropriate activities to identify the occurrence of a cybersecurity event.
   - **Respond**: Take action regarding a detected cybersecurity incident.
   - **Recover**: Maintain plans for resilience and restore any capabilities or services impaired due to a cybersecurity incident.

2. **Categories and Subcategories**: Each core function is divided into categories and subcategories that represent specific outcomes and activities.

3. **Implementation Tiers**: These tiers describe the degree to which an organization’s cybersecurity practices exhibit the characteristics defined in the framework. The tiers range from Partial (Tier 1) to Adaptive (Tier 4).

4. **Profiles**: The framework allows organizations to create a current profile and a target profile, helping them to identify gaps and plan improvements in their cybersecurity practices.

### Enhancements in Version 2.0:

- **Increased Focus on Supply Chain Security**: Emphasis on managing risks associated with supply chains and third-party relationships.
- **Integration of Privacy**: Expanded guidance on how cybersecurity practices intersect with privacy protections.
- **More Comprehensive Guidance for Small and Medium-Sized Enterprises (SMEs)**: Additional resources and recommendations tailored to the needs of smaller organizations.
- **Updates to Reflect Emerging Threats and Technologies**: Adjustments to address new and evolving cybersecurity threats and the incorporation of new technologies.

The NIST CSF 2.0 aims to provide a flexible and adaptable approach to managing cybersecurity risk, applicable across various sectors and organizational sizes. It remains a widely recognized and respected resource for organizations seeking to improve their cybersecurity posture.




## ISO/IEC 27001 and ISO/IEC 27002
---
ISO/IEC 27001 and ISO/IEC 27002 are part of the ISO/IEC 27000 family of standards, which are designed to help organizations manage information security effectively. Here’s an overview of each:

### **ISO/IEC 27001**

**ISO/IEC 27001:2013** (often referred to as ISO 27001) is the international standard that outlines the requirements for establishing, implementing, maintaining, and continually improving an Information Security Management System (ISMS). It provides a systematic approach to managing sensitive company information, ensuring it remains secure.

#### **Key Features of ISO/IEC 27001:**

- **Scope and Requirements**: It sets out the criteria for setting up an ISMS, including risk assessment and treatment processes.
- **Control Objectives and Controls**: It mandates that organizations identify risks to their information and apply appropriate controls.
- **Certification**: Organizations can be certified against ISO/IEC 27001 to demonstrate their commitment to information security.

### **ISO/IEC 27002**

**ISO/IEC 27002:2022** (the most recent version as of 2024) provides guidelines and best practices for implementing information security controls based on the requirements of ISO/IEC 27001. It is essentially a companion to ISO/IEC 27001, offering a detailed list of controls and their implementation.

#### **Key Features of ISO/IEC 27002:**

- **Control Objectives and Controls**: It includes a comprehensive set of controls grouped into domains (e.g., information security policies, organization of information security, asset management, access control).
- **Guidance on Implementation**: It provides practical advice on how to implement the controls and measure their effectiveness.
- **Alignment with ISO/IEC 27001**: While ISO/IEC 27001 specifies what controls are needed, ISO/IEC 27002 provides guidance on how to implement them effectively.

### **Relationship Between ISO/IEC 27001 and ISO/IEC 27002**

- **ISO/IEC 27001** specifies the requirements for an ISMS, including the need for a risk assessment and the selection of controls to address those risks. It provides a framework for managing information security risks systematically.
- **ISO/IEC 27002** offers detailed guidance on the specific controls that can be implemented to achieve the objectives outlined in ISO/IEC 27001. It helps organizations choose and apply the most appropriate controls based on their individual needs and risk landscape.

### **Implementation and Benefits**

- **ISO/IEC 27001** certification can help organizations demonstrate their commitment to information security to customers, partners, and stakeholders. It provides a structured approach to managing and mitigating information security risks.
- **ISO/IEC 27002** helps organizations understand and apply best practices for information security controls, making it easier to align with the requirements of ISO/IEC 27001.

Together, these standards provide a comprehensive framework for managing and improving information security within an organization.

## SOC Type 2
---
SOC 2 (System and Organization Controls 2) is a framework for managing and securing data that is particularly relevant to technology and cloud computing companies. Developed by the American Institute of Certified Public Accountants (AICPA), SOC 2 focuses on the controls and processes that service organizations use to manage data in a way that protects the privacy and confidentiality of their clients.

### **Key Features of SOC 2**

1. **Trust Service Criteria**: SOC 2 reports are based on the Trust Service Criteria, which were previously known as Trust Service Principles. These criteria are:
   - **Security**: Measures to protect systems against unauthorized access (both physical and logical).
   - **Availability**: Ensures that systems are available for operation and use as agreed upon.
   - **Processing Integrity**: Ensures that system processing is accurate, timely, and authorized.
   - **Confidentiality**: Protects information designated as confidential according to agreements or policies.
   - **Privacy**: Manages personal information in compliance with privacy policies and regulations.

2. **Types of SOC 2 Reports**:
   - **SOC 2 Type I**: Describes the system and evaluates the design of the controls at a specific point in time.
   - **SOC 2 Type II**: Provides a detailed assessment of the operational effectiveness of controls over a period of time, typically 6 to 12 months.

3. **Audit Process**: A SOC 2 audit is conducted by an independent third-party CPA firm. The audit involves reviewing the service organization’s controls, processes, and procedures to ensure they meet the Trust Service Criteria.

4. **Use Cases**: SOC 2 is especially important for service organizations that handle sensitive or critical data on behalf of their clients. It is commonly used by SaaS providers, cloud storage companies, and other technology service providers.

### **Benefits of SOC 2 Compliance**

- **Trust and Assurance**: SOC 2 compliance helps build trust with customers by demonstrating that the organization has implemented effective controls to protect data.
- **Competitive Advantage**: Having a SOC 2 report can differentiate a service provider from competitors and is often a requirement for doing business with certain clients.
- **Risk Management**: The process of obtaining SOC 2 compliance helps identify and address potential weaknesses in data security and management practices.

### **Comparison with Other Frameworks**

- **ISO/IEC 27001**: While SOC 2 focuses on specific criteria related to data security and privacy, ISO/IEC 27001 is a broader standard for establishing, implementing, maintaining, and improving an information security management system (ISMS).
- **SOC 1**: SOC 1 reports focus on controls relevant to financial reporting, whereas SOC 2 is centered on security, availability, processing integrity, confidentiality, and privacy.

SOC 2 is a widely recognized standard for data protection, particularly in the technology and cloud sectors, and is critical for organizations that handle sensitive client information.

## NERC-CIP
---
NERC-CIP (North American Electric Reliability Corporation Critical Infrastructure Protection) is a set of standards designed to enhance the security and reliability of the North American electric grid. Developed by the North American Electric Reliability Corporation (NERC), these standards provide a framework for protecting critical infrastructure within the electric power industry.

### **Key Aspects of NERC-CIP**

1. **Purpose and Scope**:
   - **Objective**: NERC-CIP aims to safeguard critical infrastructure in the electric sector from cyber threats and vulnerabilities. This includes ensuring the reliability and resilience of the bulk electric system (BES) through robust security measures.
   - **Scope**: The standards apply to entities that own, operate, or use critical infrastructure within the bulk electric system. This includes transmission operators, generation operators, and other key stakeholders in the electric grid.

2. **Core Standards**:
   The NERC-CIP standards consist of several individual requirements that cover various aspects of critical infrastructure protection. Key standards include:
   - **CIP-002**: **Critical Cyber Asset Identification** - Identifies and classifies assets that are critical to the reliability of the bulk electric system.
   - **CIP-003**: **Security Management Controls** - Defines management controls and procedures to ensure proper handling of critical cyber assets.
   - **CIP-004**: **Personnel & Training** - Establishes requirements for personnel training and security awareness.
   - **CIP-005**: **Electronic Security Perimeter(s)** - Implements measures to protect electronic access points and networks.
   - **CIP-006**: **Physical Security of Critical Cyber Assets** - Ensures physical protection of critical cyber assets.
   - **CIP-007**: **Systems Security Management** - Covers measures to protect and manage systems and controls.
   - **CIP-008**: **Incident Reporting and Response Planning** - Defines processes for reporting and responding to security incidents.
   - **CIP-009**: **Recovery Plans for Critical Cyber Assets** - Establishes plans for recovery and restoration in case of a security incident.
   - **CIP-010**: **Configuration Change Management and Vulnerability Assessments** - Provides requirements for managing system configurations and assessing vulnerabilities.
   - **CIP-011**: **Information Protection** - Ensures protection of information associated with critical cyber assets.

3. **Compliance and Enforcement**:
   - **Compliance**: Entities subject to NERC-CIP must comply with the standards, which involves implementing security measures, conducting regular assessments, and undergoing audits.
   - **Enforcement**: NERC monitors compliance through audits and assessments. Non-compliance can result in penalties and corrective actions.

4. **Updates and Evolution**:
   - **Version Updates**: The NERC-CIP standards are periodically updated to address emerging threats and technology changes. For example, NERC-CIP standards have evolved to incorporate new security practices and to address evolving cyber threats.

### **Importance and Impact**

- **Reliability**: NERC-CIP standards play a crucial role in maintaining the reliability and stability of the North American electric grid by ensuring that critical infrastructure is protected from cyber attacks and other security threats.
- **Cybersecurity**: As the electric grid becomes increasingly digital and interconnected, robust cybersecurity measures are essential to protect against disruptions and ensure continuous operation.

Overall, NERC-CIP provides a comprehensive framework for managing and mitigating risks related to critical infrastructure in the electric power industry, helping to ensure the ongoing stability and reliability of the bulk electric system.

# Models
---
---
## Cyber Kill Chain

![[Pasted image 20240912094509.png]]
The **cyber kill chain** is a model used to describe the stages of a cyber attack. It provides a structured approach to understanding and defending against cyber threats by breaking down an attack into a sequence of steps. The concept was originally developed by ==Lockheed Martin== to help organizations identify and mitigate potential attacks more effectively.

Here’s a breakdown of the stages in the traditional cyber kill chain:

1. **Reconnaissance**: The attacker gathers information about the target organization. This might involve researching company details, identifying key personnel, and discovering potential vulnerabilities. Techniques can include social engineering, scanning networks, or searching publicly available information.

2. **Weaponization**: The attacker creates or acquires tools or payloads to exploit the identified vulnerabilities. This could involve developing custom malware or leveraging existing exploits. The goal is to craft a weaponized exploit that can be delivered to the target.

3. **Delivery**: The attacker transmits the weaponized payload to the target. This could be done through various means such as phishing emails, malicious attachments, drive-by downloads, or exploiting vulnerabilities in web applications.

4. **Exploitation**: The payload is executed on the target system, exploiting a vulnerability or flaw. This stage involves the actual execution of the malicious code, which could provide the attacker with initial access to the system.

5. **Installation**: The attacker establishes a foothold on the target system. This involves installing malware or backdoors that ensure continued access and control over the compromised system.

6. **Command and Control (C2)**: The attacker establishes a communication channel with the compromised system to control it remotely. This allows them to send commands, exfiltrate data, or further manipulate the system.

7. **Actions on Objectives**: The attacker takes actions to achieve their goals, which could include data exfiltration, system manipulation, or disrupting operations. This stage involves the execution of the final objectives of the attack, such as stealing sensitive information or causing damage.

By understanding and addressing each stage of the cyber kill chain, organizations can improve their defensive strategies and enhance their ability to detect and respond to cyber threats.

---

# Methodology
---
---
## Information Warfare

**Information warfare** generally refers to the use of information and communication technologies to gain a strategic advantage over adversaries. This can include a range of activities designed to manipulate, disrupt, or damage the information systems and processes of opponents. Here’s a breakdown of what it might encompass:

1. **Cyber Espionage**: Unauthorized access to confidential information for strategic or economic gain. This can involve stealing trade secrets, personal data, or sensitive government information.

2. **Propaganda and Disinformation**: Spreading false or misleading information to influence public opinion, create confusion, or undermine trust in institutions. This could involve fake news, manipulated media, or misleading social media campaigns.

3. **Psychological Operations**: Tactics used to influence the emotions and perceptions of individuals or groups. This might include creating fear or doubt through targeted attacks or misinformation.

4. **Disruption and Sabotage**: Actions aimed at disrupting normal operations or causing damage to an organization’s infrastructure. This could include deploying malware, launching denial-of-service attacks, or other disruptive tactics.

5. **Information Manipulation**: Altering or corrupting data to mislead or create false perceptions. This can involve modifying records, falsifying documents, or other means of data tampering.


---



## Methodology of Ethical Hacking

**Hacking methodology** refers to the structured approach or systematic process that ethical hackers and cybercriminals use to conduct their activities. Understanding hacking methodologies is crucial for both offensive and defensive cybersecurity professionals. Here’s a detailed look at a common hacking methodology used by ethical hackers and security professionals:

### 1. **Planning and Preparation**

- **Objective Setting**: Define the goals of the assessment, such as identifying vulnerabilities or testing defenses.
- **Scope Definition**: Establish the boundaries of the engagement, including what systems, networks, or applications will be tested and any exclusions.
- **Rules of Engagement**: Agree on the rules with the client, such as allowable testing methods, times, and reporting protocols.

### 2. **Reconnaissance**

- **Information Gathering**: Collect information about the target organization. This includes:
  - **Passive Reconnaissance**: Gathering information without direct interaction, such as searching publicly available data (WHOIS records, social media, company websites).
  - **Active Reconnaissance**: Directly interacting with the target, such as network scanning or port scanning.

### 3. **Scanning and Enumeration**

- **Network Scanning**: Identify active devices on the network and their IP addresses. Tools like Nmap are commonly used.
- **Port Scanning**: Discover open ports and services running on those ports. This helps identify potential entry points.
- **Vulnerability Scanning**: Scan systems for known vulnerabilities using tools like Nessus or OpenVAS.
- **Enumeration**: Gather detailed information about network resources, such as user accounts, network shares, and system configurations.

### 4. **Gaining Access**

- **Exploit Vulnerabilities**: Use known vulnerabilities or misconfigurations to gain unauthorized access to the target system. This can involve:
  - **Social Engineering**: Manipulating individuals to reveal sensitive information or perform actions that compromise security.
  - **Exploiting Software Vulnerabilities**: Using exploit code to take advantage of weaknesses in software applications or operating systems.

### 5. **Maintaining Access**

- **Establish Persistence**: Implement mechanisms to ensure continued access, such as installing backdoors, creating new user accounts, or modifying system configurations.
- **Covering Tracks**: Erase or alter logs and other evidence to avoid detection and maintain stealth.

### 6. **Privilege Escalation**

- **Escalate Permissions**: Once initial access is gained, attempt to gain higher-level access (e.g., administrative privileges) to increase control over the system. This can involve exploiting additional vulnerabilities or misconfigurations.

### 7. **Data Exfiltration**

- **Collect and Extract Data**: Access and gather sensitive data, which could include personal information, financial data, intellectual property, or other valuable assets.
- **Exfiltration Techniques**: Transfer the collected data out of the target network. This could be done through various methods, such as encrypted communication channels or covert data transfers.

### 8. **Reporting and Documentation**

- **Document Findings**: Record all findings, including vulnerabilities discovered, exploits used, and data accessed. This is critical for providing a comprehensive report.
- **Prepare a Report**: Create a detailed report that includes an executive summary, technical findings, and recommendations for remediation. This helps the organization understand the risks and take appropriate actions to improve their security posture.

### 9. **Remediation and Follow-up**

- **Assist with Fixes**: Provide guidance on how to remediate identified vulnerabilities and strengthen defenses.
- **Re-testing**: After remediation, re-test the systems to ensure that vulnerabilities have been effectively addressed and that new issues have not been introduced.

### Additional Considerations

- **Ethical and Legal Considerations**: Ensure all activities are conducted with proper authorization and in compliance with legal and ethical standards.
- **Continuous Learning**: Stay updated with the latest vulnerabilities, exploits, and security trends to maintain effective testing practices.

By following a structured methodology, ethical hackers can systematically identify and address security weaknesses, while organizations can better protect themselves against malicious attacks.


---

# Others
---
---
## Incident Report Team
An **Incident Response Team (IRT)** is a specialized group within an organization responsible for managing and mitigating cybersecurity incidents. This team is crucial for ensuring that incidents are handled effectively and that the impact on the organization is minimized. Here’s an overview of the key aspects and functions of an Incident Response Team:

### 1. **Roles and Responsibilities**

- **Incident Response Manager**: Oversees the incident response process, coordinates the team's activities, and communicates with senior management. They are responsible for ensuring that the incident response plan is followed and that resources are allocated appropriately.
  
- **Incident Handlers**: Handle the day-to-day activities of responding to incidents. They investigate the nature of the incident, contain and mitigate its impact, and coordinate with other team members to address the situation.
  
- **Forensic Analysts**: Specialize in gathering and analyzing evidence from compromised systems. They work to understand the attack vector, determine what was affected, and preserve evidence for potential legal action.
  
- **Threat Intelligence Analysts**: Provide context and insight into the threat actor’s tactics, techniques, and procedures (TTPs). They use threat intelligence to understand the nature of the attack and predict possible future threats.
  
- **Communications Specialists**: Manage internal and external communications during and after an incident. They ensure that accurate information is communicated to stakeholders, including employees, customers, and, if necessary, the media.

- **Legal and Compliance Experts**: Ensure that the response actions comply with legal and regulatory requirements. They help manage legal risks and handle any legal aspects of the incident, including reporting obligations.

### 2. **Incident Response Phases**

1. **Preparation**: 
   - Develop and maintain an incident response plan.
   - Train the team and organization on incident response procedures.
   - Set up and test communication channels, tools, and technologies.

2. **Identification**: 
   - Detect and confirm the occurrence of an incident.
   - Use monitoring tools and logs to identify signs of a breach or compromise.
   - Classify the incident to determine its severity and impact.

3. **Containment**: 
   - Implement short-term and long-term containment strategies to limit the spread of the incident.
   - Isolate affected systems to prevent further damage.
   - Communicate containment actions to relevant stakeholders.

4. **Eradication**: 
   - Remove the root cause of the incident, such as deleting malicious files or closing vulnerabilities.
   - Ensure that all traces of the attack are eradicated from the environment.

5. **Recovery**: 
   - Restore and validate affected systems to normal operation.
   - Monitor systems for any signs of persistent threats or recurring issues.
   - Verify that systems are secure before returning them to normal use.

6. **Lessons Learned**: 
   - Conduct a post-incident review to analyze the response process and outcomes.
   - Document findings and update incident response plans based on lessons learned.
   - Share insights and improvements with the organization to enhance future response efforts.

### 3. **Best Practices**

- **Have an Incident Response Plan**: Develop a comprehensive plan that outlines the roles, responsibilities, and procedures for responding to incidents. Regularly review and update the plan to address new threats and vulnerabilities.
  
- **Conduct Regular Training**: Ensure that the incident response team and relevant stakeholders are trained on the latest incident response techniques and tools.
  
- **Test Your Plan**: Regularly conduct drills and tabletop exercises to test the effectiveness of your incident response plan and team readiness.

- **Leverage Threat Intelligence**: Use threat intelligence to stay informed about emerging threats and tactics used by adversaries. This information can help in anticipating and preparing for potential incidents.

- **Maintain Communication**: Ensure clear communication channels within the incident response team and with external stakeholders. Effective communication is crucial for coordinating response efforts and managing the impact of an incident.

- **Focus on Documentation**: Keep detailed records of the incident, including actions taken, decisions made, and evidence collected. This documentation is essential for analyzing the incident and meeting legal or regulatory requirements.

### 4. **Tools and Technologies**

- **Security Information and Event Management (SIEM) Systems**: For collecting, analyzing, and correlating security events and logs.
  
- **Endpoint Detection and Response (EDR) Tools**: For monitoring and responding to activities on endpoints.
  
- **Forensic Tools**: For analyzing and preserving evidence from compromised systems.

- **Incident Management Platforms**: For coordinating response activities and tracking incident progress.

An effective Incident Response Team is essential for minimizing the impact of cybersecurity incidents and ensuring a swift and organized response. By having a well-defined structure, clear processes, and the right tools, organizations can better manage and recover from security incidents.




---
# Q & A
---
### What is Information Warfare ?
Ans . [[#Information Warfare]]
##### Examples of Information Warfare ?
Ans. 
		Cyber Espionage
		Propaganda and Disinformation
		Psychological Operations
		Disruption and Sabotage
		Information Manipulation

---
### What is Cyber Kill Chain ?
Ans. [[#Cyber Killl Chain]]

##### Phases of Cyber Kill chain or Intrusion Kill Chain ?
Ans. 
		Reconnaissance
		Weaponization
		Delivery
		Exploitation
		Installation
		Command & Control (C2)
		Actions on Objective

---
### What is MITRE ATT&CK ?
Ans. [[#MITRE ATT&CK]]
##### Key Components of the MITRE ATT&CK Framework
Ans.
		Tactics
			Initial Access
			Execution
			Persistence
		Techniques
			Phishing
			Command And Scripting Interpreter
		Sub-techniques
			Command And Scripting Interpreter
				PowerShell
				Scripting
		Procedures
		Mitigation
		Detections

##### Stages the Att&ck Framework Identifies.
Ans.
		Reconnaissance
		Resource Development
		Initial Access
		Execution
		Persistence
		Privilege Escalation
		Defense Evasion
		Credential Access
		Discovery
		Lateral Movement
		Collection
		Command and Control
		Exfiltration
		Impact

---
### What is Methodology of Ethical Hacking ?
Ans. [[#Methodology of Ethical Hacking]]

##### Stages of hacking Methodology.
Ans. 
		[[#1. **Planning and Preparation**]]
		[[#2. **Reconnaissance**]]
		[[#3. **Scanning and Enumeration**]]
		[[#4. **Gaining Access**]]
		[[#5. **Maintaining Access**]]
		[[#6. **Privilege Escalation**]]
		[[#7. **Data Exfiltration**]]
		[[#8. **Reporting and Documentation**]]
		[[#9. **Remediation and Follow-up**]]

---
### What is Incident Report Team ?
Ans. [[#Incident Report Team]]

##### What are Roles in IRT Team ?
Ans. 
		Incident Response Manager
		Incident Handler
		Forensic Analysts
		Threat Intelligence Analysts
		Communication Specialists
		Legal and Compliance Experts

##### What are phases of Incident Response
Ans. 
		Preparation
		Identification
		Containment
		Eradication
		Recovery
		Lessons Learned

##### What tools and technologies are used by incident Report Team?
Ans.
		Security Information and Event Management System (SIEM)
		Endpoint Detection and Response Tools (EDR)
		Forensic Tools
		Incident Management Platforms
