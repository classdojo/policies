# ClassDojo Security Overview

At ClassDojo, safeguarding data privacy and security is a core commitment. From day one, we design our products with security and privacy at the forefront, ensuring our safeguards evolve alongside the latest industry standards.  Our [Privacy Policy](https://www.classdojo.com/privacy/) and [Student Data Privacy Addendum](https://static.classdojo.com/docs/DPA/classdojo-student-data-dpa.pdf) solidify the commitments that ClassDojo and schools make to each other, including our security and privacy commitments. 

This Security Overview provides a high-level snapshot of ClassDojo’s information security program. While this page is written for technology experts who often play a key role in assessing our policies, we recognize that data security is just as important to families, teachers, and students as it is to school officials. If you would like to find out more and access materials that are written to help you digest the more technical information here, please visit our [Privacy & Security Portal](https://www.classdojo.com/privacy-and-security/). 
 
ClassDojo operates the services offered on classdojo.com (the &quot;ClassDojo Website&quot;), including the ClassDojo platform (the &quot;ClassDojo Platform&quot;), and any associated mobile applications (the &quot;ClassDojo Apps&quot;) or products and services that Company may provide now or in the future (collectively, the &quot;Service&quot;). Capitalized terms not defined in this document, such as &quot;Student Data&quot;, are defined in our Student Data Privacy Addendum. We regularly evaluate our policies and practices to improve security and to keep up with the latest practices of the security industry. Should you have security or privacy questions, please reach out to our team at privacy@classdojo.com

* * *

## Quick Reference

- [Audits and Certifications](#audits-and-certifications)
- [Physical Security](#physical-security)
- [Infrastructure Security](#infrastructure-security)
  - [Corporate Security](#corporate-security)
  - [Cloud Security](#cloud-security)
- [Access Control and Monitoring](#access-control-and-monitoring)
  - [Access Monitoring](#access-monitoring)
  - [Audit Logging](#audit-logging)
- [Incident Response and Vulnerability Management](#incident-response-and-vulnerability-management)
  - [Incident Response](#incident-response)
  - [Vulnerability & Patch Management](#vulnerability--patch-management)
- [Product Security](#product-security)
  - [Code Analysis](#code-analysis)
  - [Credential Management](#credential-management)
  - [Responsible Disclosure](#responsible-disclosure)
  - [Secure Development Training](#secure-development-training)
  - [Software Development Lifecycle](#software-development-lifecycle)
- [IT Governance](#it-governance)
- [Disaster Recovery and Business Continuity (BC/DR)](#disaster-recovery-and-business-continuity-bcdr)
  - [Backups and Availability Control](#backups-and-availability-control)
- [Control of Instructions and Data Segregation Security](#control-of-instructions-and-data-segregation-security)
  - [Role-Based Access Control (RBAC)](#role-based-access-control-rbac)
  - [User Roles & Logical Access Controls](#user-roles--logical-access-controls)
  - [Data Security](#data-security)
- [Summary](#summary)



# ClassDojo Security Overview

## Audits and Certifications
The ClassDojo platform is undergoing SOC2 certification in 2025.

Our security program is built on the **NIST CyberSecurity Framework**, a widely adopted standard for organizing and measuring security programs. This framework is complemented by compliance with various privacy regulations such as [GDPR, COPPA, and FERPA](https://www.classdojo.com/privacycenter), modern engineering practices, and continuous innovation in security.

---

## Physical Security
Student Data is stored in the United States with our service provider, Amazon Web Services (AWS) (us-east-1).  

AWS and Google maintain physical security at their data centers:
- [AWS Data Center Controls](https://aws.amazon.com/compliance/data-center/controls/)
- [Google Data Security](https://www.google.com/about/datacenters/data-security/)

---

## Infrastructure Security

### **Corporate Security**
#### **Multi-Factor Authentication**
ClassDojo employees use two-factor authentication (2FA) for accessing company resources via Google.

#### **Disk Encryption**
We use FileVault to encrypt data on all corporate laptops.

#### **Endpoint Detection & Response**
SentinelOne is used to protect laptops from malware and cyber threats.

#### **Mobile Device Management**
We use Rippling MDM for managing and securing corporate laptops.

#### **Threat Detection**
A third-party security monitoring firm tracks security threats and events on laptops.

---

## Cloud Security

### **Cloud Workload Protection**
We monitor cloud workloads for security issues using Orca, Prowler, and other modern security tools.

### **Remote Access**
- Network access is strictly limited to authorized staff.
- VPN access is required for administrative access to AWS-hosted servers

### **Encryption at Rest**
- AWS S3 AES-256 with AWS-managed keys  
- Aurora (MySQL): AES-256 with customer-managed keys  
- Redshift AES-256 with AWS-managed keys  
- MongoDB AES-256 with keys managed by MongoDB  
- All ClassDojo laptops are encrypted by default managed by our IT and Security team.

### **Encryption in Transit**
- All ClassDojo data is encrypted in transit using TLS 1.2.  
- Our services are served via AWS Cloudfront or Elastic Load Balancers (ELB).  
- HTTP Strict Transport Security (HSTS is enforced for secure connections.

### **Firewall**
We use AWS Security Groups to limit network access.

### **IDS/IPS (Intrusion Detection & Prevention)**
AWS GuardDuty is enabled in all AWS environments and monitored by third-party Managed Detection and Response (MDR) firms.

### **Security Information and Event Management (SIEM)**
All security-related logs from cloud, endpoints, and other systems are sent to a **third-party MDR vendor for analysis**.

### **Traffic Filtering**
We leverage AWS WAF and HA-Proxy for traffic filtering and shaping.

---

## Access Control and Monitoring

### **Access Monitoring**
- Access is restricted to engineers, data scientists, product managers, and support personnel**.  
- Permissions are reviewed bi-annually and updated automatically when roles change.  
- High-priority system access requires managerial approval.

### Audit Logging
- Datadog provides real-time monitoring through logs and alerts.  
- Alerts escalate to on-call rotation engineers via PagerDuty.

---

## Incident Response and Vulnerability Management

### Incident Response
- 24/7 security monitoring is performed in collaboration with Managed Detection & Response (MDR) firms.
- Custom logging, AWS Cloudwatch, and Guard Duty are used for tracking security events.
- A structured incident response plan guides security investigations.

### Vulnerability & Patch Management
- Security tools continuously monitor for vulnerabilities and missing patches.  
- Security patches are prioritized and applied in a timely manner.  
- Automated updates are deployed when possible.

---

## Product Security

### Code Analysis
- All source code is scanned for vulnerabilities upon commit and during development.
- Scanning includes:
  - Static code analysis
  - Infrastructure-as-Code vulnerability detection
  - Source composition analysis

### Credential Management
- Secrets are securely stored in Vault, Jenkins Secrets, or GitHub Encrypted Secrets.
- User credentials are stored using a one-way salted hash, never logged or accessible by staff.

### Responsible Disclosure
We encourage security researchers to report bugs via our [bug bounty program](mailto:security@classdojo.com).

### Secure Development Training
- Engineers undergo annual security training, covering OWASP Top 10 vulnerabilities.

### Software Development Lifecycle
ClassDojo follows a secure software development lifecycle (SDLC), which includes:
- Tagging and tracking engineering work in Asana  
- Peer code reviews  
- Automated security testing before deployment  
- Continuous monitoring and rollback mechanisms  
- Canary builds for controlled feature rollouts  
- Production monitoring for performance and security  

---

## IT Governance

ClassDojo aligns IT security with compliance efforts through:
- Strong security policies  
- Regular risk assessments  
- Quarterly Executive Security & Privacy Governance meetings  
- A risk register for tracking and managing risks  

---

## Disaster Recovery and Business Continuity (BC/DR)

### Backups and Availability Control
- Daily encrypted backups stored in multiple AWS availability zones.  
- Multi-factor authentication (MFA) required for backup access.  
- Routine backup testing ensures data integrity before restoration.

---

## Control of Instructions and Data Segregation Security

### Role-Based Access Control (RBAC)
- Access is strictly limited based on role (e.g., engineers, product managers, support staff).  
- All infrastructure access is logged and monitored.  
- Third-party security monitoring ensures 24/7 detection and response.

### User Roles & Logical Access Controls
- Application roles include Student, Teacher, Parent, School Leader.  
- Logical security controls manage permissions based on user roles.

### Data Security
- ClassDojo maintains Records of Processing Activities (GDPR requirement).
- A public version of our data classification is available here:  
  - [ClassDojo Transparency Page](https://www.classdojo.com/transparency/)

---

## Summary
This Security Overview provides a high-level summary of ClassDojo’s security controls.  

For detailed policies, compliance documentation, and real-time security updates, visit our [Security Portal](https://www.classdojo.com/privacy-and-security/).  
