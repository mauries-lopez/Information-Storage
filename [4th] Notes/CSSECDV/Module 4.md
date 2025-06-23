
**Authorization**
- is the process of giving someone permission to do or have something.
- Also known as Access Control - is mediating access to resources based on identity and is generally policy-driven
- AuthN -> IAAA AuthZ -> Policy (ACL)
	- Access Control List: set of rules (like a firewall)

**Principle of Least Privilege**
- Encourages system designers and implementers to allow running code only the permissions needed to complete the required tasks and no more.
- Spans the configuration of the web and application servers through the business capabilities of business logic components.
	- API is also included

**Centralized Authorization Routines**
- Crucial for maintainability
- Problem:
	- A common mistake is to perform an authorization check by cutting and pasting an authorization code snippet into every page containing sensitive information.
	- Worse yet would be re-writing this code for every page
- Solution:
	- Well written applications centralize access control routines, so if any bugs are found, they can be fixed once, and the results apply throughout the application immediately.

**Controlling Access to Protected Resources**
- Some applications check to see if a user can undertake a particular action, but then do not check if access to all resources required to complete the requested action is allowed.
- For example, forum software may check to see if a user can reply to a previous message, but then fails to check that the requested message is not within a protected or hidden forum or thread.
	- Sa discord, baka ung rereplyan niya na message ay nasa loob pala ng admin-channel sa discord.

**Generic Types of Access Controls**
- Network Access: Ability to connect to a system or service
	- Firewall rules
- Host Access: Access to operating system functionality
	- Printers, file shared folders
- Physical Access: Locations that are housing information assets; physical access to the assets themselves.
	- Parang 2 layers ng pintuan, ung parang sa SM, ung papasok ka sa isang pintuan tapos checheck ng bag tapos isa pang pintuan.
	- Kiningston Lock
- Restricted Functions: Operations evaluated as having an elevated risk.
	- Financial transactions, changes to system configuration, or security administration

Resource access may refer not only to files and database functionality, but also to:
- Applications or APIs
- Specific Application Screens/Functions
- Specific Data Fields
- Memory
- Private/Protected Variables
- Storage Media
- Transmission Media
// In short, any object used in processing, storage, or transmission of information.

**Access Control Models**
1. Discretionary Access Controls
	- Based on the identity and need-to-know of subjects and/or the groups to which they belong.
	- They are discretionary in the sense that a subject with certain access permissions is capable of passing on that access, directly or indirectly, to other subjects.![[Screenshot 2025-06-10 at 9.40.11 AM.png]]
2. Mandatary Access Controls
	- Based on the sensitivity of the information contained in the objects / resources and a formal authorization
	- Top Secret / Secret/ Confidential 
	- They are mandatory in the sense that they restrain subjects from setting security attributes on an object and from passing on their access.
3. Role-based Access Controls (RBAC)
	- Based on the rules played by users and groups in organizational functions.
	- Roles, alternatively referred to as security groups, include collections of subjects that all share common needs for access.
	- For example:
		- Active Directory -> OU's -> Security Groups -> (a) All-Employees (b) IT-Admin (c) IT-Users
		- Pwede nalang pumili ng isang buo sa isang security group
	- Authorization for access is then provided to the role or group and inherited by members.![[Screenshot 2025-06-10 at 9.44.42 AM.png]]
4. Attribute-based Access Controls (ABAC)
	- A newer paradigm based on properties of an information exchange that may include identified attributes of the requesting entity, the resource requested, or the context of the exchange or the requested action.

**Examples of Access Controls in Software**
- Account Management
- Mapping of user rights to business and process requirements
- Mechanisms that enforce policies over information flow
- Limits on the number of concurrent sessions
- Session lock after a period of inactivity
- Session termination after a period of inactivity, total time of user or time of day
- Limitations on the number of records returned from a query (data mining)
- Features enforcing policies over segregation of duties
- Segregation and management of privileged user accounts
- Implementation of the principle of least privilege for granting access
- Requiring VPN (virtual private network) for access
- Dynamic reconfiguration of user interfaces based on authorization
- Restriction of access after a certain time of day

