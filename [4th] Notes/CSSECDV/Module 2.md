
**Thread Modeling**

//Risk Ranking: 5 levels (5 - critical, 4 - high, 3 - medium, 2 - low, 1 - info)

Evaluation Methodologies
- Manual Inspection and REview
	- Human-driven review that analyzes the impact of people, policies, and processes to security
	- Focused on analyzing existing artifacts and interviewing individuals
	- Has the ability to test the SDLC as a whole
	- “Trust-but-verify”
	- Pros:
		- Requires no supporting technology
		- Flexible
		- Encourages teamwork
		- Can be applied early in the SDLC
	- Cons:
	- Time consuming
	- Needed artifacts are sometimes missing
	- High level of human skill and thought

**Penetration Testing**
- The ‘art’ of testing deployed applications remotely without knowledge of its workings
- A staple of network security testing
- Uses tools and manual techniques to verify the security of an application
- Pros:
	- Fast and cheap
	- Relatively lower skill-set required
	- Tests code in production
- Cons:
	- Late in the SDLC
	- Impact testing only

| Black                                    | Gray           | White                |
| ---------------------------------------- | -------------- | -------------------- |
| Blind                                    | Some knowledge | All info             |
| No knowledge but I only know ONE DOMAIN. | —              | Insiders disgruntled |
| Simulate outsiders                       | —              | —                    |

**Source Code Review**
- S.A.S.T (Static Application Security Testing)
- This is done by Q.A team
- Manual checking of the source code for problems
- Provides reviewers with a lot more information than other approaches
- Serious vulnerabilities missed, are seen in code
- Requires more effort (time) than other techniques
- Pros:
	- Complete and effective
	- Accurate
	- Fast
- Cons:
	- High level of skill
	- Compiled libraries are not covered
	- Run-time errors may be missed
	- Actual code vs. reviewed code

**Threat**
- Potential or actual undesirable event that may be malicious or incidental
- Malicious -> DoS Attack
- Incidental -> Failure of a storage device (Fatigue)
- Accidents -> man-made (MOST COMMON!)
- Legal Liabilities (e.g. government laws & regulations)
- Cost of Quality

**Threat Model**
- A structure representation of all the information that affects the security of an application
- By doing this, we can proactively find vulnerabilities before they are exploited.
- A process for capturing, organizing, and analyzing information that affects the security of an application
- Enables informed decision-making about application security risk
- In addition to producing a model, typical threat modeling efforts also produce a prioritized list of security improvements to the concept, requirements, design, or implementation.
- Pros:
	- Attacker’s PoV
	- Flexible
	- Early in the SDLC
- Cons:
	- New Technique
	- Good Threat Model is not a good software
- Why is Threat Modeling Important?
	- Objectives:
		- A procedure for optimizing Network/Application/Internet Security by identifying objectives and vulnerabilities
		- Defining countermeasures to prevent, or mitigate the effects of, threats to the system.
	- Key Benefits:
		- Helps secure web applications by identifying threats early.
		- Reduces future costs by fixing problems before they become major issues.
		- Aligns with security standards, making it easier to meet compliance regulations like SOC2 and PCI DSS.
		- Provides a clear “line of sight” across a project that justifies security efforts
		- Allows security decisions to be made rationally
		- Produces an assurance argument that can be used to explain and defend the security of an application
		- An assurance argument starts with a few high level claims, and justifies them with either sub claims or evidence
- Prerequisities
	- Clearly defined security policies
		- Governance laws and regulations
	- Awareness of compliance and regulatory requirements
		- PCI DSS
	- Mature SDLC process
		- Well documented
		- Measured (KPI)
		- Managed
	- Will actually use the threat model

**Threat Modeling in SDLC**
- Best applied continuously throughout a software development project
- Essentially the same at different levels of abstraction, although the information gets more and more granular throughout the life cycle
- A high-level threat model shoudl be defined in the concept or planning phase and then refined throughout the lifecycle
- As more details are added to the system, new attack vectors are created and exposed
- Ongoing threat modeling process should examin, diagnose, and address these threats
- A natural part of refining a system for new threats to be exposed
- For example:
	- If using java, you take on the responsibility to identify the new threats that are created by that choice
	- Even implementation choices such as using regular expressions for validation introduce potential new threats to deal with

**Getting Standard in Threat Modeling**
- To understand whether an application is secure enough or not, you have to search out combinations of these ingredients that lead to realistic threats.
- The real trick to threat modeling is not wasting time on threats that are too unlikely or too inconsequential
- There is no “right” way to evaluate the search space of possible threats, but there are “wrong” ways
- Attempting to or evaluating all the possible combinations of threat agent, attack, vulnerability, and impact is a waste of time and effort
- It is more productive to focus on finding high likelihood and high impact threats.

**Generic Steps**
1. Assessment Scope
2. System Modeling
3. Identify Threats
4. Evaluation or Impact on the Business
5. Examining the Threat History
6. Identify Vulnerabilities
7. Developing a Security Threat Response Plan

**Assessment Scope**
- Identifying tangible assets, like database of information or sensitive files is usually easy
- Understanding the capabilities provided by the application and valuing them is more difficult
- Less concrete things, such as reputation and goodwill are the most difficult to measure, but are often the most critical

**Identify Threat Agents**
- A key part of the threat model is characterization of the different groups of people who might be able to attack your application
- These groups should include insiders and outsiders, performing both inadvertent mistakes and malicious attacks

**Understand Existing Countermeasures**
- The model must include the existing countermeasures

**Identify Exploitable Vulnerabilities**
- Once you have an understanding of the security in the application, you can then analyze for new vulnerabilities
- The search is for vulnerabilities that connect the possible attacks you’ve identified to the negative consequences you’ve identified

**Prioritize Identified Risks**
- Prioritization is everything in threat modeling, as there are always lots of risks that simply dont rate any attention.
- For each threat, you estimate a number of likelihood and impact factors to determine an overall risk or severity level

**Identify Countermeasures to Reduce Threat**
- The last step is to identify countermeasures to reduce the risk to acceptable levels
- Immediate or Permanent

**Key Steps**
1. Identify Objectives: understand what assets need protection, such as customer data or the system itself.
2. Define the scope: determine what parts of the system should be included in the threat model.

**Techniques**
- Data Flow Diagram (DFDs): These help map how data moves through a system.
- Trust Boundaries: Areas where data passes between trusted and untrusted zones.

**Data Flow Diagrams (DFD)**
- A graphical representation that illustrates “how” information flows through systems, including web applications.
- Used to identify potential security risks by visualizing data transformation, storage location, and component interactions within the application architecture
- Allows developers, security consultants, and stakeholders to recognize possible vulnerabilities or points where data might be compromised, essential for implementing effective security measures.

**Components of a Data Flow Diagram**
- Entities: External entities that interact with the system (e.g., users, external services)
- Processes: Functions or activities that receive data, transform it, and output it.
- Data Stores: Repositories where data is stored for further processing or archival
- Data Flows: Paths through which data travels between entities, processes, and data stores.

**Importance in Secure Web Development**
- Using DFDs in web development helps map out data origin, interaction, and where it ends up, which is crucial for:
	- Ensuring data is protected throughout its journey
	- Understanding boundary crossing points, which can be prime targets for data breaches.
	- Identifying unsanitized inputs that may lead to vulnerabilities like SQL Injection or XSS.
	- Structuring security protocols around vulnerable and sensitive data interactions.

![](CSSECDV/Img/image9.png)

![](CSSECDV/Img/image8.png)

**Trust Boundaries**
- A conceptual boundary within a system that separates areas of differing trust levels.
- Trust boundaries exist where data moves from one trust level to another (e.g., from an external user to an internal system)
- These boundaries represent potential attack points and require security controls.
- Areas where attacks are mostly like to occur. Requires additional security measures such as:
	- Encryption
	- Input Validation
	- Access control mechanisms
- Identify and Protect Trust Boundaries early in the design process
- Use DFDs to map data flows and visualize where boundaries exist.
- Apply appropriate controls like firewalls, encryption, and secure coding practices at boundary crossings.

**Identify Threat Agents**
- Categories:
	- External Threats: Hackers, malware, phishing attacks.
	- Internal Threats: Malicious insiders, poorly configured systems.
- Methods:
	- STRIDE: Helps classify threats like Spoofing, Tampering, and Denial of Service
	- DREAD: Measures threat impact based on Damage, Reproducibility, Exploitability, Affected Users, and Discoverability.

**STRIDE/DREAD**
- Developed by Microsoft and suggested by OWASP for use
- Provides a classification scheme for known threats and the likelihood of realization
- Inherently built for use with applications
- Simple to use and deploy
- Developing a thorough model may be difficult at first for inexperienced users.
- STRIDE
	- Spoofing Identity (Integrity)
	- Tampering with Data (Integrity)
	- Repudiation (Integrity)
	- Information Disclosure (Confidentiality)
	- Denial of Service (Availability)
	- Elevation of Privilege (Integrity)
	- //These attacks C.I.A
- DREAD
	- Damage Potential
	- Reproducibility
	- Exploitability
	- Affected Users
	- Discoverability

**Spoofing**
- Attacks involve an attacker impersonating something or someone else to gain unauthorized access to systems, thereby breaching authenticity and potentially confidentiality.

**Tampering**
- Involves the unauthorized modification of data or code. This threatens the integrity of systems by altering data or codebase without permission

**Repudiation**
- Occur where there is an ability for someone to deny a transaction or activity. Non-repudiation mechanisms like logging and audit trails are compromised, impacting accountability.

**Information Disclosure**
- Involves the unauthorized access to or exposure of data, thus compromising confidentiality

**Denial of Service**
- An attack aim to make a service unavailable for its intended users, imapcting the availability aspect of the CIA triad.

**Elevation of Privilege**
- This threat occurs when an attacker gains elevated access to resources that are normally protected from an application or user, compromising authorization mechanisms.

DREAD: Damage Potential

|   |   |
|---|---|
|How much damage will it cost?|   |
|Nothing|0|
|Individual User Data|4|
|System-Wide Damage|10|

DREAD: Reproducibility

|                                                 |     |
| ----------------------------------------------- | --- |
| How easy is it to reproduce the threat exploit? |     |
| Incredibly difficult/impossible                 | 0   |
| A few steps with authorized access              | 5   |
| No tools needed and without authorization       | 10  |

DREAD: Exploitability

|   |   |
|---|---|
|What do you need to exploit this?|   |
|Advanced programming knowledge, skills and tools|0|
|Malware or preexisting tool online|5|
|No tools or just a browser|10|

DREAD: Affected Users

|   |   |
|---|---|
|How many users will be affected?|   |
|None|0|
|Some|5|
|All|10|

DREAD: Discoverability

|   |   |
|---|---|
|How easy will it be to discover this threat?|   |
|Very hard or impossible, may require access to source code or administrator rights|0|
|Can be identified through network monitoring and guessing|5|
|Details are available to the public|9|
|Visible in the browser and no tools needed|10|

Threat Modeling Process
- Define Phase
	- Identify security objectives and assets
	- Profile the application
- Model Phase
	- Decompose the application
	- Identify threats and vulnerabilities
- Measure Phase
	- Document the threats
	- Prioritize threats

1. Identify security objectives
	- Prior to any action, the direction of an organization in terms of security should be understood.
	- Ideally, this should be performed by business leadership, development team, and the QA team.
	- Consider the following:
		- Identity
		- Financial
		- Reputation
		- Privacy and regulatory
		- Availability
2. Application Profiling
	-  Provides a high-level view of the application and its components
	- Achieved through the analysis of an application’s architecture and design documents
	- The following artifacts may help:
		1. Class Diagrams
		2. ERD Diagrams
		3. Data Flow Diagrams
		4. Use Case Diagrams
	-  Points to consider:
		1. Physical topology
		2. Logical topology
		3. Components, services, protocols
		4. Actors
		5. Data Elements
		6. Access control matrix
		7. Technologies
		8. External dependencies
3. Decompose the Application
	- From the top, drill down to specific components for analysis
	- Identify features, behaviors, and requirements that can impact security given how the application functions
	- Tasks:
		1. Identify trust boundaries
		2. Identify entry points
		3. Identify exit points
		4. Identify data flow
		5. Identify privileged code
		6. Document security profile
4. Identify Threats
	- Once a thorough understanding of the application is achieved, specific threats to the application should be identified
	- Focus should be on known threats
	- Tracking threats:
		1. Threat Graph
		2. Structured Threat List

		Threat Graph
		- Places developers in the mindset of an attacker
		- Brainstorming possible threat scenarios
		- Represented as a tree:
			- Root - attacker’s objective/attack type
			- Child Node - vulnerability
			- Bottom Node - security control

		Threat List
		- Goal based approach to threat modeling
		- More structured than the threat graph
		- Can show cross-correlation between different threats
		- Possible with:
			- STRIDE
			- OCTAVE
			- NSA IAM

		Identify Threats
		- Common Threats:
			- Ignorant User
			- Accidental Discoverer
			- Curious Attacker
			- Script Kiddies
			- Insider
- //STRIDE may be used to classify threats based on the intent

DREAD - Discoverability

| Dimensions                                       | Attack Vectors                           |
| ------------------------------------------------ | ---------------------------------------- |
| Targets (Processes)                              | Web Services<br><br>Background Processes |
| Targets (Processes) constrained by Access Rights | Microsoft SQL running on Administrator   |
| Targets (Data)                                   | Flat files, virtual directories          |
| Enablers (Process)                               | XPCMDSHELL Enabled                       |
| Channels                                         | NULL Sessions                            |

Identifying Attack Surfaces
- Attack surfaces are areas in an application that may be leveraged for an attack
- Howard, Pincus, and Wing identified 3 dimensions:
	- Targets and Enablers
	- Channels and Protocols
	- Access Rights

5. Document Threats
	- All outputs from the previous steps should be recorded due to the iterative nature of threat modeling
	- Diagram vs. Text
	- A standard template should be used to ensure consistency
		1. Threat Identifier
		2. Description
		3. Targets
		4. Attack Techniques
		5. Impact
		6. RIsk
6. Prioritize Threats
	- Threat modeling to assist in decision making
	- Prioritizing the threats identifies helps development teams identify and rank which to tackle first
	- Common approaches:
		1. Delphi Ranking
		2. Average Ranking (DREAD)
		3. Probability x Impact (P x I) Ranking

Average Ranking

![](CSSECDV/Img/image10.png)

Probability x Impact Ranking
- A more scientific approach to computing for risk
- Typical in Risk Management calculations
- Organizations use the following formula

![](CSSECDV/Img/image4.png)![](CSSECDV/Img/image3.png)

**Key Components**
- Threats: Identified risks, such as SQL injection or DoS attacks
- Vulnerabilities: Weak points in the system
- Impact and Mitigation: The potential damage and how to stop it

**Countermeasures**
- Preventive Controls: Encryption, firewalls, secure coding
- Detective Controls: Intrusion detection systems (IDS), logging, and monitoring
- Corrective Controls: Backups, incident response plans.