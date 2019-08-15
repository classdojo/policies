# ClassDojo Security Whitepaper

ClassDojo, operates the services offered on classdojo.com (the &quot;ClassDojo Website&quot;), including the ClassDojo platform (the &quot;ClassDojo Platform&quot;), and any associated mobile applications (the &quot;ClassDojo Apps&quot;) or products and services that Company may provide now or in the future (collectively, the &quot;Service&quot;).

Protecting data privacy and security is a top priority for ClassDojo. Our [Privacy Policy](https://www.classdojo.com/privacy/) and [Student Data Privacy Addendum](https://na3.docusign.net/Member/PowerFormSigning.aspx?PowerFormId=6d8f3d18-2a69-4248-aced-5b53d46969c3&env=na3-eu1) solidify the commitments that ClassDojo and schools make to each other, including our security and privacy commitments. Capitalized terms not defined in this document, such as &quot;Student Data&quot;, are defined in our Student Data Privacy Addendum. We regularly evaluate our policies and practices to improve security and to keep up with the latest practices of the security industry.

This document is designed to provide technical readers, such as Chief Information Officers or Chief Technology Officers at school districts, additional clarity and specifics about our security commitments. While this document is written for technology experts who often play a key role in assessing our policies, we recognize that data security is just as important to families, teachers, and students as it is to school officials. If you would like to find out more and access materials that are written to help you digest the more technical information here, please visit our [Privacy Center](https://www.classdojo.com/privacycenter/). Additionally, should you have security or privacy questions, please reach out to our team at privacy@classdojo.com

* * *

## Quick Reference

- [Infrastructure Security](#infrastructure-security)
  - [Encryption at Rest and In Transit](#encryption-at-rest-and-in-transit)
  - [Network Security](#network-security)
  - [Patching](#patching)
  - [Backups and Availability Control](#backups-and-availability-control)
- [Physical Security](#physical-security)
  - [Physical Access Controls](#physical-access-controls)
  - [Virtual Access Control](#virtual-access-control)
  - [Data Access Control](#data-access-control)
  - [Disclosure Control](#disclosure-control)
  - [Entry Control](#entry-control)

## Infrastructure Security

### Encryption at Rest and In Transit

Access to the ClassDojo Service occurs via encrypted connections

(HTTP over TLS, also known as HTTPS) which encrypt all data before it leaves the ClassDojo Service&#39;s servers and protects that data as it transits over the internet.All of our Services are in Amazon Web Services (AWS) and served from either Cloudfront or Elastic Load Balancer (ELB). We use HTTP Strict Transport Security to ensure that pages are loaded over HTTPS connections and our TLS configuration receives an A+ from [Qualys SSL Labs](https://www.ssllabs.com/ssltest/analyze.html?d=classdojo.com&latest).

Student Data is stored at our Service Provider, AWS, and the following applies to their technical and organizational measures. In addition, we secure decentralized data processing equipment and personal computers. All personally identifiable information is encrypted at rest using modern encryption algorithms. In AWS S3, we use AES­256 with AWS managed keys, in Aurora (MySql) we use AES-256 with customer managed keys and in Redshift we use AES-256 with AWS managed keys. Additionally, we use MongoDB with AES-256 with keys managed by AWS For more information on these vendors please see our [Third Party Service Providers chart](http://www.classdojo.com/third-party-service-providers/).

### Network Security

The ClassDojo Services use AWS, to host the infrastructure. AWS undergoes strict ongoing security assessments from external audit firms to ensure compliance with security standards including ISO 27001, SOC 2, PCI DSS Level 1, and FISMA. See [https://aws.amazon.com/compliance/programs/](https://aws.amazon.com/compliance/programs/) for more details.

Network access to the ClassDojo Services infrastructure is highly restricted. AWS hosted infrastructure resides in a dedicated Virtual Private Cloud (VPC) which is designed to ensure that only authorized traffic over approved ports is allowed. We use ThreatStack to monitor for suspicious activity.

### Patching

We use automated processes to regularly install security updates on the infrastructure that powers the ClassDojo Services, these processes include:

- AWS Managed Services (e.g., Relational Database Service):** AWS proactively notifies our engineering team when updates are available and we apply them in a timely fashion.
- AWS EC2:** All EC2 instances are monitored by ThreatStack and AWS inspector and updates are applied in a timely fashion
- Classdojo Application:** Monitored by Snyk.io and Github for vulnerabilities and they are updated in a timely fashion

### Backups and Availability Control

We have a data backup and recovery capability that is designed to provide a timely restoration of the ClassDojo Services, with minimal data loss, in the case of catastrophic failure. These backups are encrypted and stored in multiple availability zones. Additional technical and organizational measures to ensure that Student Data are protected against accidental destruction or loss (physical/logical) include:

- Uninterruptible power supply (UPS);
- Remote storage; and
- Firewall systems.

*Note: Student Data is stored at our Service Provider - currently AWS - and the above applies to their technical and organizational measures as well as any other relevant [Service Providers](https://www.classdojo.com/third-party-service-providers/), such as MongoDB. In addition, we have a disaster recovery plan in place.*

## II.Physical Security

### Physical Access Controls

Technical and organizational measures to prevent unauthorized persons from gaining access to the data processing systems available in premises and facilities (including databases, application servers and related hardware), where Student Data are Processed\*, include:

- Establishing security areas, restriction of access paths;
- Establishing access authorizations for employees and third parties;
- Access control system (ID reader, magnetic card, chip card);
- Key management, card-keys procedures;
- Door locking (electric door openers etc.);and
- Surveillance facilities, video/CCTV monitor, alarm system.

*Note: The ClassDojo Services are currently hosted in AWS and Student Data is stored at our Service Provider - currently AWS – which employs industry- leading physical security measures to protect their data centers and the above applies to their technical and organizational measures. These security features are regularly audited by third ­party auditors. You can learn more about AWS&#39; physical security [here.](https://aws.amazon.com/compliance/data-center/controls/) We also utilize MongoDB. You can learn more about Mongo DB&#39;s security [here](https://www.mongodb.com/cloud/atlas/security). In addition, we secure decentralized data processing equipment and personal computers.*

### Virtual Access Control

Technical and organizational measures to prevent data processing systems used for Student Data from being used by unauthorized persons include:

- User identification and authentication procedures;
- ID/password security procedures (special characters, minimum length, change of password); and
- Encryption of archived data media.

### Data Access Control

Access to the ClassDojo Services infrastructure is highly restricted. We limit access to individuals who need access to do their jobs such as engineers, data scientists, product managers, and support personnel. All access to our infrastructure is logged. All access to our infrastructure requires the use of strong passwords and multi­factor authentication.

Technical and organizational measures to ensure that persons entitled to use a data processing system gain access only to such Student Data in accordance with their access rights, and that Student Data cannot be read, copied, modified or deleted without authorization, include:

- Internal policies and procedures;
- Control authorization schemes;
- Differentiated access rights (profiles, roles, transactions and objects);
- Monitoring and logging of accesses;
- Disciplinary action against employees who access personally identifiable information without authorization;
- Reports of access;
- Access procedure;
- Change procedure;
- Deletion procedure;

### Disclosure Control

Technical and organizational measures to ensure that Student Data cannot be read, copied, modified or deleted without authorization during electronic transmission, transport or storage on storage media (manual or electronic), and that it can be verified to which companies or other legal entities Student Data are disclosed, include:

- Encryption/tunneling;
- Logging; and
- Transport security.

### Entry Control

Technical and organizational measures to monitor whether Student Data have been entered, changed or removed (deleted), and by whom, from data processing systems, include:

- Logging and reporting systems; and
- Audit trails and documentation.
