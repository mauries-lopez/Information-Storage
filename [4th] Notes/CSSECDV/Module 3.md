"I Triple-A Services"
- Identification
- Authentication (AuthN)
- Authorization (AuthZ)
- Accounting (Logging)

**Authentication**
- Authentication is the process of verification that an individual, entity, or website is who it claims to be.
- Authentication in the context of web applications is commonly performed by submitting a username or ID and one or more items of private information that only is a given user should know.
	- Some ways to authenticate:
		- Something you know (e.g. password/personal identification number (PIN))
		- Something you have (e.g., cryptographic identification device, token)
		- Something you are  (e.g., biometric, retina, iris)
- You need to implement Multi-Factor Authentication
	- Something you know + Something you have or other combinations
	// Something you know + Something you know is not allowed.

**User ID**
- Make sure your username/user IDs are case insensitive.
	- Use 'smith' and user 'Smith' should be the same user.
- Usernames should also be unique.
- For high security applications usernames could be assigned and secret instead of user-defined public data.

**Implement Proper Password Strength Controls**
- A key concern when using passwords for authentication is password strength.
- A "strong" password policy makes it difficult or even improbable for one to guess the password through either manual or automated means.
- Consider the following:
	- Password length (8 characters is enough)
	- Password complexity (Combinations of letters, numbers, special characters)
	- Password topologies 

**Implement Secure Password Recovery Mechanism**
- It is common for an application to have a mechanism that provides a means for a user to gain access to their account in the event they forget their password.
	- Password Reset (Forgotten Password)
		- You can use these to reset your password:
			- Back-up email
			- Mobile (OTP)
			- Secret Questions (e.g. Personal Questions)

**Store Passwords in a Secure Fashion**
- It is critical for an application to store a password using the right cryptographic technique.
- Hashing
	- Bcrypt
	- Scrypt
	- Fragon2
May possible na if same ung password natin then may same hash tayo kaya ang gagawin ay "salt" para mag randomize 

**Transmit Passwords Only Over TLS or Other Strong Transport**
- The login page and all subsequent authenticated pages must be exclusively accessed over Transport Layer Security (TLS) or other transport.
- The initial login page, referred to as the "login landing page", must be served over TLS or other strong transport.
	- LetsEncrypt (Free Service)
		- Can provide free TLS certificate
- Failure to utilize TLS or other strong transport for the login landing page allows an attacker to modify the login form action, causing the user's credentials to be posted to an arbitrary location.
- Failure to utilize TLS or other strong transport for authenticated pages after login enables an attacker to view the unencrypted session ID and compromise the user's authenticated session.

**Require Re-authentication for Sensitive Features**
- Require the current credentials for an account before updating sensitive account information (password, email) or before sensitive transactions (shipping a purchase to a new address).
- Attacker may be able to execute sensitive transactions through a Cross-Site Request Forgery (CSRF) or Cross-site Scripting (XSS) attack without needing to know the user's current credentials.
- Attacker may also get temporary physical access to a user's browser or steal their session ID to take over the user's session.

**Consider Strong Transaction Authentication**
- Some applications should use a second factor to check whether a user may perform sensitive operations.

**Authentication and Error Messages**
- Incorrectly implemented error messages in the case of authentication functionality can be used for the purposes of user ID and password enumeration.
- An application should respond (both HTTP and HTML) in a generic manner.

**Authentication and Error Messages**
- An application should respond with a generic error messages regardless of whether the user ID or password was incorrect.
- It should also give no indication to the status of an existing account.
	- Incorrect Response Examples:
		- "Login for User foo: invalid password"
	- Correct Response Example:
		- "Login failed; Invalid user ID or password"
- The application may return a different HTTP Error code depending on the authentication attempt response.
- It may respond with a 200 for a positive result and a 403 for a negative result.
- Even though a generic error page is shown to a user, the HTTP response code may differ which can leak information about whether the account is valid or not.
	- HTTP Status Codes:
		- 1xx: Informational
		- 2xx: Success
		- 3xx: Redirection
		- 4xx: Client Error
		- 5xx: Server Error

**Prevent Brute-Force Attacks**
- If an attacker can guess passwords without the account becoming disabled due to failed authentication attempts, the attacker has an opportunity to continue with a brute force attack until the account is compromised.
- Password lockout mechanisms should be employed that lock out an account if more than a preset number of unsuccessful login attempts are made.
- Multi-factor authentication is a very powerful deterrent when trying to prevent brute force attacks since the credentials are a moving target.
- When multi-factor is implemented and active, account lockout may no longer be necessary.

**Logging and Monitoring**
- Enable logging and monitoring of authentication functions to detect attacks/failures on a real time basis.
	- Ensure that all failures are logged and reviewed.
	- Ensure that all password failures are logged and reviewed.
	- Ensure that all account lockouts are logged and reviewed.

**Use of authentication protocols that require no password**
- While authentication through a user/password combination and using multi-factor authentication is considered it isn't considered the best option or even safe.
	- Example:
		- Third party applications that desire connecting to the web application, either from a mobile device, another website, desktop or other situations.
	- Extends the attack surface into their hands, where it isn't in your control.