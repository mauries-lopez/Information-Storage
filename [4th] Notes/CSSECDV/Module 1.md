Introduction to Information Security & Secure Development

*// Data Breaches on Yahoo, Marriott, Equifax, Capital One, Comelec*

**What is Information?** 
- Information is an asset to all individuals & businesses.
**What is Information Security?**
- It refers to “the protection of assets (information) in order to achieve CIA triad (Confidentiality, Integrity, and Availability)”

// Confidentiality vs Disclosure
// Integrity vs Modification/Destruction
// Availability vs Disruption

Key Concepts
![](CSSECDV/Img/image5.png)
*This will have trade-offs. For example, I am a depositor of a bank, I dont care about Confidentiality gusto ko lang ng availability para kahit anong oras pwede ako makapag withdraw at lalo na ang Integrity, sigurado na tama ung mga nababawas at pumapasok.*

- **Confidentiality**
	- Cryptography and Data Management
	- The state in which data is only disclosed to authorized subjects. “Secret”
	- For example, when submitted to a website, your personal data should only be used or accessed exclusively by designated staff in that company for the purposes agreed.
	- Layers of Protection
		- Defense-in-depth
			- Backup in cloud
			- Full disk encryption
			- MDM
			- Web Application Firewall: filters traffic
			- Load Balancer
			- Geolocation Restrictions
	- Need to do encryption:
		- Data in Transit: TLS 1.2 (HTTPS) (SSL is deprecated)
		- Data in Rest: Full Disk Encryption
		- Data in Processing:
	- AWS (Cloud)
		- Key Management Service (KMS)
- Integrity
	- Non-repudiation and Digital Signatures
		- Non-repudiation: The User cannot deny performing an action.
	- The state in which data is not modified/deleted without prior authorization.
	- For example, when submitted to a website, your personal data should not be altered in any way during data transmission or by the website company.
- Availability
	- Redundancy and Back-ups
		- Back-ups: Restore (This needs to be tested in a test server kasi baka ung nag down na ung server tapos nalaman na ung restored data ay hindi pala kumpleto)
	- The state in which assets are made available in a timely manner to authorized subjects.
	- For example, you should be able to access and check your personal data kept on a website at any time.
	- Cloud Architecture
		- Resiliency
		- Auto scaling
	- If you can ping your server, it is up and running (Good), and with 20-50ms (Good)
		- But if it reaches 100ms to 200ms (Bad), then it is “Lagging”
	- Always check uptime and latency
// Chaos Monkey : looks for single point of failure to have “lessons learned”

**Security**
- 2 Acceptable Levels
	- Risk Appetite: This depends on their business model. For example, buying 2 ISP. If 1 ISP lang at nag down pa to, ang laki ng revenue loss. Mas malaki ung revenue loss na to at mas viable na bumili nalang ng 2 ISP.

**Assets**
- Any item, tangible or intangible, with value to an individual or organization.
- Identifying assets is the first step in improving your security. You should know who or what you need to protect.

// C-level : Bagay na may epekto sa C.I.A; critical ung bagay na to sa company.

**Threat**
- A threat is what can go wrong because of the exploitation of vulnerabilities or an attack on assets, such as data theft or unauthorized modification of the data.
- Combination of asset + vulnerability
- Common threats of web apps:
	- SQL Injection
	- Broken Authentication
	- CSRF
-  OWASP Top 10 ← List of threats in web applications ranking

**Threat Agent**
- An individual or group that is capable of carrying out a particular threat.

**Vulnerability**
- An inherent weakness in the network and network devices.
- It could be hardware or software, or both.

**Attack**
- An unauthorized action with the intent to cause damage, or hinder or breach security of a network
- Active attacks
- An attack is launched by intruders to damage the network and network resources, such as end-point devices, servers, or desktops, which are vulnerable.

**Impact**
- A measure of the potential damage caused by a particular threat.
- For example, operational disruption, reputational damage, loss of customer trust, and intellectual property theft.
- High-impact threats need more attention than low-impact threats.

**Risk**
- Severity of impact
- The probability that a particular threat directed towards a specific vulnerability will occur.

![](CSSECDV/Img/image6.png)

Risk = likelihood x impact
- High-likelihood but low impact; nagkamali lang ng three times ung password, malolock out account. (Brute-force)
- Low-likelihood but high impact;
- High-likelihood and high impact; stealing information

// Always patch any problems within 24 hours

**Control**
- Safeguard or countermeasure that you put in place in order to avoid, detect, counteract, or minimize potential threats against your information, systems, or other assets.
- Three types
	- Technical (Logical): Firewalls, Encryption, Anti-Malware
	- Administrative: Documents, Process, Policies, User Training Awareness, Non-Disclosure Agreement (NDA)
	- Physical: Door locks, Guards, Server Room, K9, bollards
- This can be preventive para mahinto na agad before pa mag occur.
- This can be detective threats before they materialize.
- This can be corrective through the defense-in-depth.

// defense-in-depth: layer by layer of defense![](CSSECDV/Img/image11.png)

![](CSSECDV/Img/image1.png)

**Software Engineering**
- The process of solving customers’ problems by the systematic development and evolution of large, high-quality software systems within cost, time and other constraints.
- Triple constraints: ![](CSSECDV/Img/image7.png)

- Challenges:
	- Lack of understanding of user needs
	- Unclear scope
	- Lack of change management
	- Poor project planning
	- Communication problems
	- Teamwork problems
	- Security Issues
- Software Development Life Cycle (SDLC)
	- Basic Phases:
		1. Requirements: follow compliance (PCI DSS, Privacy, Data Privacy Act, BSP Regulation)
		2. Analysis
		3. Design: implement security and threat models
		4. Implementation: secure coding standards
		5. Post-delivery: penetration testing (showing the vulnerabilities), deployment (environment such as production, test <- sa test branch siya ilalagay para matest ung mga vulnerability)

// Bakit hindi nalang lagi i-update ung mga vulnerabilities na nadedetect? Kailangan ng maintenance window atleast 1 hr kasi ang need to atleast ipatch. Ang vulnerabilities usually show 3x a day, 4x a week, 10x a month kaya kung lagi nag papatch lagi rin mag dodown, eh may agreement nga kayo na SLA 99.999% lagi dapat available ung system.

- SDLC Models
	- Code-and-Fix
	- Waterfall
	- Iterative
	- Incremental
	- Agile
	- Scrum

**Model-View-Controller**
- A software architecture ideally suited to web applications
- Separates the logic from the user interface
- Allows individual components to be tested independently of one another
- In terms of security, provides an extra layer of protection through isolation
- Before, monolithic architecture, all-in-one na kaya sa isang server nandon na ung web application, database, backups.
- Ngayon, 3-tier architecture, hiwalay ang web, app, and database. Per tier, may authentication.
- Model:
	- Encapsulates functionality and represents data in a structured manner
	- Provides an abstraction between low level primitives and the Controller and View.
- View:
	- Also called the presentation layer, the view provides users with a frontend with….
- Controller
	- Contains the application or business logic needed to process user data
	- This acts as the mediator between the Model and the View
	- Apart from processing, it should contain code needed to protect the application from threats.

![](CSSECDV/Img/image2.png)

---

**Security Principles for Secure Software Design**
- Principles and practices that applications should adhere to in order to remain secure
- Should be adapted based on the needs of the current project
- Applies not only to web applications, but to IT systems as a whole

**Minimize Attack Surface Area**
- Attack Surface Area? Entry points in an application that may allow attackers to gain entry and eventually exploit vulnerabilities and compromise the application.
- Goal: reduce the number of ways an attacker can exploit the application
- How: limiting entry points, removing unnecessary features, enforcing the principle of least privilege, etc.

// https runs on 443; http runs on 80; mysql or database runs on 3306
// limit the web application running on 443.
// Geolocation restriction can also minimize the attack surface area.

**Secure Defaults**
- These settings should be highly secure and enabled by default as much as possible
- Security is built-in from the start to reduce the chance of misconfiguration and additional vulnerabilities
- Dapat may bare minimum policies, such as setting up a password.
- For example: MFA, no default credentials, password polices, authentication (2fa or mfa)

**Principle of Least Privilege**
- Making sure that users and systems are given only the minimum access that they need while interacting with the application.

**Principle of Defense in Depth**
- Also known as layered security
- Implementing multiple security controls to protect an application.
- If one layer is breached, there are still other layers to minimize impact and deter the attacker.

**Fail Securely**
- Assume that your security controls are going to fail at some point.
- Applications should still respond accordingly in the case of an error or failure to maintain security
- Proper error handling, error messages that do not leak sensitive information (T.M.I), and disabling debugging mode

// Fail open: parang “emergency exit”
// Fail close

**External Systems are Insecure**
- Consider that not all external systems are safe
- Third-party services, APIs, and user inputs.
- Always monitor and log the interaction to and from these external dependencies
- Do proper research before use such as existing vulnerabilities

**Separation of Duties “Rotation”**
- No single role should have too much authority
- User with more duties = more susceptible to making poor decisions and committing mistakes (This can be considered as a single point of failure)
- Assign different users to different roles such as sales manager and product manager.

// Single person risk: all in one na ung access sa taong ito sa buong company. To mitigate this, “N of control” meaning marami na sila may all in one access kaya kapag may nag resign, hindi gaano maapektohan.

**Security through Obscurity is not Security**
- An application’s security does not rely entirely on secrets or information not known to many people.
- Not disclosing details such as system details and security controls used does not really improve the security of the application
- Do not use hidden URLs and/or hardcoded credentials in code

**Simplicity**
- Simpler design is easier to test
- Complex systems have more potential vulnerabilities and prone to user misconfiguration

**Fix Issues Correctly**
- Understand the root cause (1) of security issues before applying a fix
- Apply comprehensive fixes (2) that fully eliminate vulnerabilities, not just mitigate them partially
	- Immediate fix: naaayos pero mag error ulit. For example, storage capacity.
	- Permanent fix
- Test fixes thoroughly to ensure they do not introduce new security issues
- Follow security best practices and use proven techniques instead of custom or temporary solutions.

**Secure Coding Principles**

**Characteristics of Secure Organizations**
- Organizational management with security champions
	- Security champions: leaders who understand the importance of security.
- Proper information security policies
- Development methodologies with security checkpoints
- Secure release and configuration management


**Naming Conventions**
- Structured and consistent rules for naming variables, functions, files, and database elements to enhance code readability, maintainability, and security.
- Proper naming conventions reduce security risks such as confusion, accidental exposure of sensitive data, and vulnerabilities from insecure identifiers.
- For example, country-code-city-...; PH-LAG/BNN/CAB-CORE-01/02; project_name_var