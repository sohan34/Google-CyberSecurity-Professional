# Course 5 — Module 2

## Table of Contents

- [Principle of Least Privilege](#principle-of-least-privilege)
- [Data Lifecycle and Data Governance](#data-lifecycle-and-data-governance)
- [Privacy, Security, and Regulations](#privacy-security-and-regulations)
- [Encryption](#encryption)
- [Hashing](#hashing)
- [Single Sign-On and Multi-Factor Authentication](#single-sign-on-and-multi-factor-authentication)
- [Least Privilege, Separation of Duties, and IAM](#least-privilege-separation-of-duties-and-iam)
- [Terms and Definitions](#terms-and-definitions-course-5-module-2)

---

## Principle of Least Privilege

Security controls are essential to keeping sensitive data private and safe. One of the most common controls is the **principle of least privilege (PoLP)**, also called **least privilege**.

Least privilege is a security concept in which a user is only granted the minimum level of access and authorization required to complete a task or function.

It is a fundamental security control that supports the confidentiality, integrity, and availability (CIA) triad of information.

### How Least Privilege Reduces Risk

Implementing least privilege can greatly reduce the risk of costly incidents like data breaches by:

- Limiting access to sensitive information
- Reducing the chances of accidental data modification, tampering, or loss
- Supporting system monitoring and administration

Least privilege reduces the likelihood of a successful attack by connecting specific resources to specific users and placing limits on what they can do.

Clearly defining who or what your users are is usually the first step in implementing least privilege effectively.

**Note:** Least privilege is closely related to the security principle of **separation of duties**, which divides tasks and responsibilities among different users to prevent giving a single user complete control over critical business functions.

### Determining Access and Authorization

To implement least privilege, access and authorization must be determined first.

There are two questions to ask:

- Who is the user?
- How much access do they need to a specific resource?

A user can refer to:

- A person, like a customer, employee, or vendor
- A device
- Software connected to the business network

Every user should have their own account. Accounts are typically stored and managed within an organization’s directory service.

### Common Types of User Accounts

- **Guest accounts:** Provided to external users who need to access an internal network, like customers, clients, contractors, or business partners
- **User accounts:** Assigned to staff based on their job duties
- **Service accounts:** Granted to applications or software that needs to interact with other software on the network
- **Privileged accounts:** Have elevated permissions or administrative access

It is best practice to determine a baseline access level for each account type before implementing least privilege.

The appropriate access level can change from one moment to the next. For example, a customer support representative should only have access to your information while they are helping you. Your data should become inaccessible when they are no longer assisting you.

Least privilege can only reduce risk if user accounts are routinely and consistently monitored.

**Pro tip:** Passwords play an important role when implementing least privilege. Even if user accounts are assigned appropriately, an insecure password can compromise your systems.

### Auditing Account Privileges

Setting up the right user accounts and assigning the appropriate privileges is a helpful first step. Periodically auditing those accounts is a key part of keeping systems secure.

There are three common approaches to auditing user accounts:

- Usage audits
- Privilege audits
- Account change audits

#### Usage Audits

A usage audit reviews which resources each account is accessing and what the user is doing with the resource.

Usage audits help determine whether users are acting in accordance with security policies and whether permissions can be revoked because they are no longer being used.

#### Privilege Audits

Users tend to accumulate more access privileges than they need over time. This is known as **privilege creep**.

Privilege audits assess whether a user’s role is aligned with the resources they can access.

#### Account Change Audits

Account directory services keep records and logs associated with each user. Changes to an account can be saved and used to audit the directory for suspicious activity, like multiple attempts to change an account password.

Performing account change audits helps ensure that all account changes are made by authorized users.

**Note:** Most directory services can be configured to alert system administrators of suspicious activity.

### Key Takeaways

- Least privilege is a security control that can reduce the risk of unauthorized access to sensitive information and resources.
- Setting up user accounts with the right access and authorization is an important step toward implementing least privilege.
- Auditing user accounts and revoking unnecessary access rights helps maintain confidentiality, integrity, and availability.

---

## Data Lifecycle and Data Governance

Organizations handle a large amount of data that must be kept private. Data can be vulnerable whether it is at rest, in use, or in transit. Regardless of the state it is in, information should be kept private by limiting access and authorization.

In security, data vulnerabilities are often mapped in a model known as the **data lifecycle**.

### The Data Lifecycle

The data lifecycle is an important model that security teams consider when protecting information. It influences how they set policies that align with business objectives. It also plays an important role in the technologies security teams use to make information accessible.

The data lifecycle has five stages:

- Collect
- Store
- Use
- Archive
- Destroy

Protecting information at each stage means keeping it accessible and recoverable should something go wrong.

### Data Governance

Businesses handle massive amounts of data every day. New information is constantly being collected from internal and external sources. A structured approach to managing data is the best way to keep it private and secure.

**Data governance** is a set of processes that define how an organization manages information.

Governance often includes policies that specify how to keep data:

- Private
- Accurate
- Available
- Secure

Effective data governance is a collaborative activity that relies on people. Data governance policies commonly categorize individuals into specific roles:

- **Data owner:** The person that decides who can access, edit, use, or destroy their information
- **Data custodian:** Anyone or anything responsible for the safe handling, transport, and storage of information
- **Data steward:** The person or group that maintains and implements data governance policies set by an organization

Businesses store, move, and transform data using a wide range of IT systems. Data governance policies often assign accountability to data owners, custodians, and stewards.

**Note:** As a data custodian, you will primarily be responsible for maintaining security and privacy rules for your organization.

### Protecting Data at Every Stage

Most security plans include a specific policy that outlines how information will be managed across an organization. This is known as a **data governance policy**.

These documents clearly define procedures that should be followed to keep data safe. They place limits on who or what can access data.

Security professionals are important participants in data governance. As a data custodian, you will be responsible for ensuring that data is not damaged, stolen, or misused.

### Legally Protected Information

Data is more than just a bunch of 1s and 0s being processed by a computer. Data can represent someone’s personal thoughts, actions, and choices.

For this reason, data owners should be the ones deciding whether or not to share their data. Protecting a person’s data privacy decisions must always be respected.

Securing data can be challenging because data owners generate more data than they can manage. As a result, data custodians and stewards sometimes lack direct, explicit instructions on how they should handle specific types of data.

Governments and other regulatory agencies have bridged this gap by creating rules that specify the types of information organizations must protect by default:

- **PII:** Personally identifiable information, or any information used to infer an individual’s identity and information that can be used to contact or locate someone
- **PHI:** Protected health information
  - In the U.S., regulated by HIPAA
  - In the EU, has a similar definition but is regulated by GDPR
- **SPII:** A specific type of PII that falls under stricter handling guidelines
  - The S stands for sensitive
  - This type of PII should only be accessed on a need-to-know basis, such as a bank account number or login credentials

It is important to protect all types of personal information from unauthorized use and disclosure.

### Key Takeaways

- Many organizations have data governance policies that outline how they protect sensitive information.
- As a data custodian, you will play a key role in keeping information accessible and safe throughout its lifecycle.
- There are various types of information and controls you will encounter in the field.
- Protecting personal information from unauthorized use and disclosure is essential.

---

## Privacy, Security, and Regulations

Security and privacy have a close relationship. People have the right to control how their personal data is collected and used. Organizations also have a responsibility to protect the information they collect from being compromised or misused.

### Information Security vs. Information Privacy

Security and privacy are often used interchangeably outside of this field, but they represent specific functions:

- **Information privacy:** The protection from unauthorized access and distribution of data
- **Information security (InfoSec):** The practice of keeping data in all states away from unauthorized users

The key difference is:

- **Privacy** is about providing people with control over their personal information and how it is shared
- **Security** is about protecting people’s choices and keeping their information safe from potential threats

For example, a retail company might want to collect specific kinds of personal information for marketing purposes, like age, gender, and location. How this private information will be used should be disclosed to customers before it is collected. Customers should also be given an option to opt out.

Once the company obtains consent to collect personal information, it might implement specific security controls to protect that private data from unauthorized access, use, or disclosure.

**Note:** Privacy and security are both essential for maintaining customer trust and brand reputation.

### Why Privacy Matters in Security

Data privacy and protection became a major issue in the late 1990s. At that time, tech companies began storing and sharing access to information about user behavior for business purposes.

Eventually, this led to global discussion about whether organizations had the right to collect and share private data. The issue of data security also became a greater concern because the more data organizations collected, the more vulnerable it was to abuse, misuse, or theft.

Many organizations became more transparent about how they collected, stored, and used information. They also began implementing more security measures to protect people’s data privacy. However, without clear rules in place, protections were inconsistently applied.

**Note:** The more data is collected, stored, and used, the more vulnerable it is to breaches and threats.

### Notable Privacy Regulations

Businesses are required to abide by certain laws to operate. Privacy regulations exist to protect a user from having their information collected, used, or shared without consent. Regulations may also describe the security measures that need to be in place to keep private information away from threats.

Three of the most influential industry regulations are:

- **GDPR**
- **PCI DSS**
- **HIPAA**

#### GDPR

**GDPR** is a set of rules and regulations developed by the European Union (EU) that puts data owners in total control of their personal information.

Under GDPR, personal information includes:

- Name
- Address
- Phone number
- Financial information
- Medical information

GDPR applies to any business that handles the data of EU citizens or residents, regardless of where the business operates.

#### PCI DSS

**PCI DSS** is a set of security standards formed by major organizations in the financial industry.

This regulation aims to secure credit and debit card transactions against data theft and fraud.

#### HIPAA

**HIPAA** is a U.S. law that requires the protection of sensitive patient health information.

HIPAA prohibits the disclosure of a person’s medical information without their knowledge and consent.

**Note:** These regulations influence data handling at many organizations around the world even though they were developed by specific nations.

### Security Assessments and Audits

Businesses should comply with important regulations in their industry. Doing so validates that they have met a minimum level of security while also demonstrating their dedication to maintaining data privacy.

Meeting compliance standards is usually a continual, two-part process of security audits and assessments:

- **Security audit:** A review of an organization’s security controls, policies, and procedures against a set of expectations
- **Security assessment:** A check to determine how resilient current security implementations are against threats

For example, if a regulation states that multi-factor authentication (MFA) must be enabled for all administrator accounts, an audit might check those user accounts for compliance. After the audit, the internal team might perform a security assessment and determine many users are using weak passwords. Based on that assessment, the team could enable MFA on all user accounts to improve their security posture.

**Note:** Compliance with legal regulations, such as GDPR, can be determined during audits.

Security audits are usually performed less frequently, approximately once per year, and may be performed both internally and externally by different third-party groups. Security assessments are usually performed more frequently, about every three to six months, and are typically performed by internal employees as preparation for a security audit.

### Key Takeaways

- Protecting and governing the use of sensitive data helps maintain customer trust.
- Security professionals should think about data and privacy in these terms.
- Organizations commonly use security assessments and audits to evaluate gaps in security plans.
- Delaying assessment results can lead to fines or data breaches.

---

## Encryption

Previously, you learned these terms:

- **Encryption:** The process of converting data from a readable format to an encoded format
- **Public key infrastructure (PKI):** An encryption framework that secures the exchange of online information
- **Cipher:** An algorithm that encrypts information

Encryption is useful for transforming information into a form that unintended recipients cannot understand.

There are two main types of encryption:

### Symmetric Encryption

Symmetric encryption uses a single secret key to exchange information.

Because it uses one key for encryption and decryption, the sender and receiver must know the secret key to lock or unlock the cipher.

### Asymmetric Encryption

Asymmetric encryption uses a public and private key pair for encryption and decryption of data.

- The public key is used to encrypt data
- The private key decrypts it
- The private key is only given to users with authorized access

### The Importance of Key Length

Ciphers are vulnerable to **brute force attacks**, which use a trial-and-error process to discover private information.

In modern encryption, longer key lengths are considered more secure because they create more possibilities that an attacker needs to try.

One drawback of long encryption keys is slower processing time. Shorter key lengths are generally less secure, but they are faster to compute. Fast data communication while keeping information safe is a balancing act.

### Approved Algorithms

Many web applications use a combination of symmetric and asymmetric encryption to balance user experience with safeguarding information.

#### Symmetric Algorithms

**Triple DES (3DES)** is a block cipher because of the way it converts plaintext into ciphertext in blocks.

Its origins trace back to the Data Encryption Standard (DES), which was developed in the early 1970s. DES was one of the earliest symmetric encryption algorithms and generated 64-bit keys, though only 56 bits are used for encryption.

Triple DES applies the DES algorithm three times using three different 56-bit keys, resulting in an effective key length of 168 bits.

Despite the longer keys, many organizations are moving away from using Triple DES due to limitations on the amount of data that can be encrypted. However, Triple DES is likely to remain in use for backward compatibility.

**Advanced Encryption Standard (AES)** is one of the most secure symmetric algorithms today.

AES generates keys that are:

- 128 bits
- 192 bits
- 256 bits

AES 128-bit keys are considered safe from brute force attacks. It is estimated that brute forcing an AES 128-bit key could take a modern computer billions of years.

#### Asymmetric Algorithms

**Rivest Shamir Adleman (RSA)** is one of the first asymmetric encryption algorithms and produces a public and private key pair.

RSA key sizes are:

- 1,024 bits
- 2,048 bits
- 4,096 bits

RSA is mainly used to protect highly sensitive data.

**Digital Signature Algorithm (DSA)** is a standard asymmetric algorithm introduced by NIST in the early 1990s.

DSA also generates key lengths of 2,048 bits and is widely used today as a complement to RSA in PKI.

### Generating Keys

These algorithms must be implemented when an organization chooses one to protect their data.

One way this is done is using **OpenSSL**, an open-source command-line tool used to generate public and private keys. OpenSSL is commonly used by computers to verify digital certificates exchanged as part of PKI.

**Note:** OpenSSL is just one option. There are various others available that can generate keys with common algorithms.

In early 2014, OpenSSL disclosed a vulnerability known as the **Heartbleed bug**, which exposed sensitive data in the memory of websites and applications. Although unpatched versions still exist, the bug was patched later that year. Many businesses today use secure versions of OpenSSL, showing the importance of using up-to-date software.

### Obscurity Is Not Security

In cryptography, a cipher must be proven unbreakable before claiming it is secure.

According to **Kerckhoff’s principle**, cryptography should be designed so that all the details of an algorithm, except for the private key, can be known without sacrificing security.

For example, all the details about how AES encryption works can be accessed online, and it is still unbreakable.

Sometimes organizations implement their own custom encryption algorithms. There have been instances where those secret cryptographic systems were quickly cracked after being made public.

**Pro tip:** A cryptographic system should not be considered secure if it requires secrecy around how it works.

### Encryption Is Everywhere

Companies use both symmetric and asymmetric encryption. They often work together, balancing security with user experience.

For example, websites tend to use asymmetric encryption to secure small blocks of important data. Usernames and passwords are often secured with asymmetric encryption during login requests. Once a user gains access, the rest of the web session often switches to symmetric encryption for speed.

Using data encryption is increasingly required by law. Regulations like **FIPS 140-3** and **GDPR** outline how data should be collected, used, and handled. Achieving compliance is critical to demonstrating to business partners and governments that customer data is handled responsibly.

### Key Takeaways

- Symmetric encryption uses a single secret key.
- Asymmetric encryption uses a public and private key pair.
- Their algorithms create different key sizes.
- Both types of encryption are used to meet compliance regulations and protect data online.

---

## Hashing

Hash functions are important controls that are part of every company’s security strategy. Hashing is widely used for authentication and **non-repudiation**, the concept that the authenticity of information cannot be denied.

Previously, you learned that hash functions are algorithms that produce a code that cannot be decrypted. Hash functions convert information into a unique value that can be used to determine integrity.

### Origins of Hashing

Hash functions have been around since the early days of computing. They were originally created as a way to quickly search for data.

They are designed to represent data of any size as small, fixed-size values, or **digests**. Using a **hash table**, a data structure used to store and reference hash values, these small values became a more secure and efficient way for computers to reference data.

One of the earliest hash functions is **Message Digest 5 (MD5)**. Ronald Rivest of MIT developed MD5 in the early 1990s to verify that a file sent over a network matched its source file.

MD5 converts data into a 128-bit value. In a hash table, this appears as a string of 32 characters. Altering anything in the source file generates an entirely new hash value.

Generally, the longer the hash value, the more secure it is. It was not long after MD5’s creation that practitioners discovered 128-bit digests resulted in a major vulnerability.

### Hash Collisions

One flaw in MD5 is a characteristic of all hash functions. Hash algorithms map any input, regardless of length, into a fixed-size value of letters and numbers.

Because there are infinite possible inputs but only a finite set of outputs, collisions can happen.

**Hash collision:** An instance when different inputs produce the same hash value

MD5 values are limited to 32 characters in length. Because of the limited output size, the algorithm is considered vulnerable to hash collision.

Attackers can carry out **collision attacks** to fraudulently impersonate authentic data.

### Next-Generation Hashing

To avoid hash collisions, functions that generated longer values were needed. MD5’s shortcomings gave way to the **Secure Hashing Algorithms (SHA)** family.

NIST approves each of these algorithms. Numbers beside each SHA function indicate the size of its hash value in bits. Except for SHA-1, which produces a 160-bit digest, these algorithms are considered collision-resistant.

Five functions make up the SHA family:

- SHA-1
- SHA-224
- SHA-256
- SHA-384
- SHA-512

### Secure Password Storage

Passwords are typically stored in a database where they are mapped to a username. The server receives an authentication request containing the user’s credentials. It then looks up the username in the database, compares it with the password, and verifies that it matches before granting access.

This is safe unless an attacker gains access to the user database. If passwords are stored in plaintext, an attacker can steal that information and use it to access company resources.

Hashing adds an additional layer of security. Because hash values cannot be reversed, an attacker would not be able to steal someone’s login credentials if they managed to gain access to the database.

### Rainbow Tables

A **rainbow table** is a file of pre-generated hash values and their associated plaintext.

They are like dictionaries of weak passwords. Attackers with access to a password database can use a rainbow table to compare hashes against possible values.

### Adding Salt

Functions with larger digests are less vulnerable to collision and rainbow table attacks. But no security control is perfect.

**Salting** is an additional safeguard used to strengthen hash functions.

A **salt** is a random string of characters added to data before it is hashed. The added characters produce a more unique hash value, making salted data resilient to rainbow table attacks.

For example, if a database contains several hashed entries for the password `password`, and those passwords are salted, each entry will be different. An attacker using a rainbow table would be unable to find matching values for `password` in the database.

### Key Takeaways

- Hashing is used to validate integrity and reduce the chance of data breaches.
- Not all hashing functions provide the same level of protection.
- Rainbow table attacks are more likely to work against shorter or weaker hashes like MD5.
- Salting strengthens hash functions and helps protect sensitive data.

---

## Single Sign-On and Multi-Factor Authentication

Most companies help keep data safely locked up behind authentication systems. Usernames and passwords are the keys that unlock information for most organizations. But are those credentials enough?

Information security often focuses on managing a user’s access and authorization to information.

Previously, you learned about the three factors of authentication:

- Knowledge
- Ownership
- Characteristic

**Single sign-on (SSO)** and **multi-factor authentication (MFA)** are two technologies that are commonly used to implement these authentication factors.

### A Better Approach to Authentication

**Single sign-on (SSO)** is a technology that combines several different logins into one.

More companies are turning to SSO for three reasons:

- It improves the user experience by eliminating the number of usernames and passwords people have to remember
- It lowers costs by streamlining how connected services are managed
- It improves security by reducing the number of access points attackers can target

SSO became available in the mid-1990s as a way to combat **password fatigue**, which refers to people’s tendency to reuse passwords across services.

### How SSO Works

SSO works by automating how trust is established between a user and a service provider. Rather than placing the responsibility on an employee or customer, SSO solutions use trusted third parties to prove that a user is who they claim to be.

This is done through the exchange of encrypted access tokens between the identity provider and the service provider.

SSO implementations commonly rely on two authentication protocols:

- **LDAP** — mostly used to transmit information on-premises
- **SAML** — mostly used to transmit information off-premises, like in the cloud

**Note:** LDAP and SAML are often used together.

### Limitations of SSO

Usernames and passwords alone are not always the most secure way to protect sensitive information. SSO provides useful benefits, but there is still a risk associated with using one form of authentication.

For example, a lost or stolen password could expose information across multiple services.

### MFA to the Rescue

**Multi-factor authentication (MFA)** requires a user to verify their identity in two or more ways to access a system or network.

MFA is similar to using an ATM:

- Insert a debit card as one form of identification
- Enter a PIN as a second form of identification

Combined, both steps are used to verify identity before authorizing access.

### Strengthening Authentication

MFA builds on the benefits of SSO. It works by having users prove that they are who they claim to be.

A user must provide:

- **Something a user knows:** Most commonly a username and password
- **Something a user has:** Normally received from a service provider, like a one-time passcode (OTP) sent via SMS
- **Something a user is:** Physical characteristics like fingerprints or facial scans

Requiring multiple forms of identification is effective, especially in cloud environments. MFA can reduce the risk of authenticating the wrong users by requiring forms of identification that are difficult to imitate or brute force.

### Key Takeaways

- Implementing SSO and MFA improves security without sacrificing user experience.
- Passwords alone are a serious vulnerability.
- SSO reduces points of entry.
- Combining SSO and MFA can protect information while keeping the user experience streamlined.

---

## Least Privilege, Separation of Duties, and IAM

Security is about ensuring that processes and technologies create a secure environment that supports a defense strategy. A key to doing this is implementing two fundamental security principles that limit access to organizational resources:

- The principle of least privilege
- Separation of duties

Both principles support each other.

For example:

- According to least privilege, a person who needs permission to approve purchases from the IT department should not have permission to approve purchases from every department.
- According to separation of duties, the person who can approve purchases from the IT department should be different from the person who can input new purchases.

In other words:

- **Least privilege** limits the access an individual receives
- **Separation of duties** divides responsibilities among multiple people to prevent any one person from having too much control

**Note:** Separation of duties is sometimes referred to as segregation of duties.

Previously, you learned about the authentication, authorization, and accounting (AAA) framework. Many businesses used this model to implement these principles and manage user access.

Another major framework is **identity and access management (IAM)**.

### Identity and Access Management (IAM)

Identity and access management (IAM) is a collection of processes and technologies that helps organizations manage digital identities in their environment.

Both AAA and IAM systems are designed to:

- Authenticate users
- Determine access privileges
- Track activities within a system

Either model is more than a single system. They each consist of a collection of security controls that ensure the right user is granted access to the right resources at the right time and for the right reasons.

A user can be:

- A person
- A device
- Software

### Authenticating Users

To ensure the right user is attempting to access a resource, some form of proof is required that the user is who they claim to be.

Authentication factors include:

- **Knowledge:** Something the user knows
- **Ownership:** Something the user possesses
- **Characteristic:** Something the user is

Authentication is mainly verified with login credentials.

SSO and MFA are also used to authenticate individuals and systems.

**Pro tip:** Another way to remember this model is: something you know, something you have, and something you are.

### User Provisioning

Back-end systems need to verify whether the information provided by a user is accurate. To accomplish this, users must be properly provisioned.

**User provisioning** is the process of creating and maintaining a user’s digital identity.

For example, a college might create a new user account when a new instructor is hired. The new account is configured to provide access to instructor-only resources while they are teaching.

Security analysts are routinely involved with provisioning users and their access privileges.

**Pro tip:** Another role analysts have in IAM is to deprovision users. This removes a user’s access rights when they should no longer have them.

### Granting Authorization

If the right user has been authenticated, the network should ensure the right resources are made available.

Three common frameworks for authorization are:

- Mandatory access control (MAC)
- Discretionary access control (DAC)
- Role-based access control (RBAC)

#### Mandatory Access Control (MAC)

MAC is the strictest framework.

Authorization is based on a strict need-to-know basis. Access to information must be granted manually by a central authority or system administrator.

MAC is commonly applied in law enforcement, military, and other government agencies where users must request access through a chain of command.

MAC is also known as non-discretionary control because access is not given at the discretion of the data owner.

#### Discretionary Access Control (DAC)

DAC is typically applied when a data owner decides appropriate levels of access.

One example is when the owner of a Google Drive folder shares editor, viewer, or commenter access with someone else.

#### Role-Based Access Control (RBAC)

RBAC is used when authorization is determined by a user’s role within an organization.

For example, a user in the marketing department may have access to user analytics but not network administration.

### Access Control Technologies

Users often experience authentication and authorization as a single, seamless experience.

That is due in large part to access control technologies configured to work together. These tools provide the speed and automation needed to monitor and modify access rights. They also reduce errors and potential risks.

An organization’s IT department may develop and maintain customized access control technologies on its own. A typical IAM or AAA system consists of:

- A user directory
- Tools for managing data in that directory
- An authorization system
- An auditing system

Some organizations create custom systems to tailor them to their security needs. However, building an in-house solution comes at a steep cost of time and resources.

Instead, many organizations license third-party solutions that offer a suite of tools to quickly secure their information systems.

### Key Takeaways

- Controlling access requires a collection of systems and tools.
- IAM and AAA are common frameworks for implementing least privilege and separation of duties.
- Security analysts may be responsible for user provisioning and collaboration with IAM or AAA teams.
- These models help ensure the right user gets access to the right resources at the right time and for the right reasons.

### Resources for More Information

The identity and access management industry is growing rapidly.

**IDPro** is a professional organization dedicated to sharing essential IAM industry knowledge.

---

## Terms and Definitions — Course 5, Module 2

| Term | Definition |
|---|---|
| Access controls | Security controls that manage access, authorization, and accountability of information |
| Algorithm | A set of rules used to solve a problem |
| Application programming interface (API) token | A small block of encrypted code that contains information about a user |
| Asymmetric encryption | The use of a public and private key pair for encryption and decryption of data |
| Basic auth | The technology used to establish a user’s request to access a server |
| Bit | The smallest unit of data measurement on a computer |
| Brute force attack | The trial and error process of discovering private information |
| Cipher | An algorithm that encrypts information |
| Cryptographic key | A mechanism that decrypts ciphertext |
| Cryptography | The process of transforming information into a form that unintended readers can’t understand |
| Data custodian | Anyone or anything that’s responsible for the safe handling, transport, and storage of information |
| Data owner | The person that decides who can access, edit, use, or destroy their information |
| Digital certificate | A file that verifies the identity of a public key holder |
| Encryption | The process of converting data from a readable format to an encoded format |
| Hash collision | An instance when different inputs produce the same hash value |
| Hash function | An algorithm that produces a code that can’t be decrypted |
| Hash table | A data structure that's used to store and reference hash values |
| Identity and access management (IAM) | A collection of processes and technologies that helps organizations manage digital identities in their environment |
| Information privacy | The protection of unauthorized access and distribution of data |
| Multi-factor authentication (MFA) | A security measure that requires a user to verify their identity in two or more ways to access a system or network |
| Non-repudiation | The concept that the authenticity of information can’t be denied |
| OAuth | An open-standard authorization protocol that shares designated access between applications |
| Payment Card Industry Data Security Standards (PCI DSS) | A set of security standards formed by major organizations in the financial industry |
| Personally identifiable information (PII) | Any information used to infer an individual's identity |
| Principle of least privilege | The concept of granting only the minimal access and authorization required to complete a task or function |
| Protected health information (PHI) | Information that relates to the past, present, or future physical or mental health or condition of an individual |
| Public key infrastructure (PKI) | An encryption framework that secures the exchange of online information |
| Rainbow table | A file of pre-generated hash values and their associated plaintext |
| Salting | An additional safeguard that’s used to strengthen hash functions |
| Security assessment | A check to determine how resilient current security implementations are against threats |
| Security audit | A review of an organization's security controls, policies, and procedures against a set of expectations |
| Security controls | Safeguards designed to reduce specific security risks |
| Separation of duties | The principle that users should not be given levels of authorization that would allow them to misuse a system |
| Session | A sequence of network HTTP basic auth requests and responses associated with the same user |
| Session cookie | A token that websites use to validate a session and determine how long that session should last |
| Session hijacking | An event when attackers obtain a legitimate user’s session ID |
| Session ID | A unique token that identifies a user and their device while accessing a system |
| Single Sign-On (SSO) | A technology that combines several different logins into one |
| Symmetric encryption | The use of a single secret key to exchange information |
| User provisioning | The process of creating and maintaining a user's digital identity |
