Previously, you learned that security involves protecting organizations and people from threats, risks, and vulnerabilities. Understanding the current threat landscapes gives organizations the ability to create policies and processes designed to help prevent and mitigate these types of security issues. In this reading, you will further explore how to manage risk and some common threat actor tactics and techniques, so you are better prepared to protect organizations and the people they serve when you enter the cybersecurity field. 

## Risk management

A primary goal of organizations is to protect assets. An **asset** is an item perceived as having value to an organization. Assets can be digital or physical. Examples of digital assets include the personal information of employees, clients, or vendors, such as: 

- Social Security Numbers (SSNs), or unique national identification numbers assigned to individuals 
    
- Dates of birth
    
- Bank account numbers
    
- Mailing addresses
    

Examples of physical assets include:

- Payment kiosks
    
- Servers
    
- Desktop computers
    
- Office spaces
    

Some common strategies used to manage risks include:

- **Acceptance**: Accepting a risk to avoid disrupting business continuity
    
- **Avoidance**: Creating a plan to avoid the risk altogether
    
- **Transference**: Transferring risk to a third party to manage
    
- **Mitigation**: Lessening the impact of a known risk

-----
### **Risks**

A **risk** is anything that can impact the confidentiality, integrity, or availability of an asset. A basic formula for determining the level of risk is that risk equals the likelihood of a threat. One way to think about this is that a risk is being late to work and threats are traffic, an accident, a flat tire, etc. 

There are different factors that can affect the likelihood of a risk to an organization’s assets, including:

- **External risk:** Anything outside the organization that has the potential to harm organizational assets, such as threat actors attempting to gain access to private information
    
- **Internal risk:** A current or former employee, vendor, or trusted partner who poses a security risk
    
- **Legacy systems:** Old systems that might not be accounted for or updated, but can still impact assets, such as workstations or old mainframe systems. For example, an organization might have an old vending machine that takes credit card payments or a workstation that is still connected to the legacy accounting system.
    
- **Multiparty risk:** Outsourcing work to third-party vendors can give them access to intellectual property, such as trade secrets, software designs, and inventions.
    
- **Software compliance/licensing:** Software that is not updated or in compliance, or patches that are not installed in a timely manner
    

There are many resources, such as the NIST, that provide lists of [cybersecurity risks](https://www.nist.gov/itl/smallbusinesscyber/cybersecurity-basics/cybersecurity-risks). Additionally, the Open Web Application Security Project (OWASP) publishes a standard awareness document about the [top 10 most critical security risks](https://owasp.org/www-project-top-ten/) to web applications, which is updated regularly.

----
### **Vulnerabilities**

A **vulnerability** is a weakness that can be exploited by a threat. Therefore, organizations need to regularly inspect for vulnerabilities within their systems. Some vulnerabilities include:

- **ProxyLogon:** A pre-authenticated vulnerability that affects the Microsoft Exchange server. This means a threat actor can complete a user authentication process to deploy malicious code from a remote location.
    
- **ZeroLogon:** A vulnerability in Microsoft’s Netlogon authentication protocol. An authentication protocol is a way to verify a person's identity. Netlogon is a service that ensures a user’s identity before allowing access to a website's location.
    
- **Log4Shell:** Allows attackers to run Java code on someone else’s computer or leak sensitive information. It does this by enabling a remote attacker to take control of devices connected to the internet and run malicious code.
    
- **PetitPotam:** Affects Windows New Technology Local Area Network (LAN) Manager (NTLM). It is a theft technique that allows a LAN-based attacker to initiate an authentication request.
    
- **Security logging and monitoring failures:** Insufficient logging and monitoring capabilities that result in attackers exploiting vulnerabilities without the organization knowing it
    
- **Server-side request forgery:** Allows attackers to manipulate a server-side application into accessing and updating backend resources. It can also allow threat actors to steal data.