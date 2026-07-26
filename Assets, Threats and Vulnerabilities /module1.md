# Course 5 — Module 1

## Risk, Threat, and Vulnerability

When security events occur, you need to work closely with others to address the problem. Doing so quickly requires clear communication between you and your team.

Previously, you learned about three foundational security terms:

- **Risk:** Anything that can impact the confidentiality, integrity, or availability of an asset
- **Threat:** Any circumstance or event that can negatively impact assets
- **Vulnerability:** A weakness that can be exploited by a threat

These words may be used interchangeably in everyday life, but in security they represent specific concepts when responding to and planning for security events.

### Security Risk

Security plans are all about how an organization defines risk. This definition can vary widely by organization.

A risk is anything that can impact the confidentiality, integrity, or availability of an asset.

One way to interpret risk is to consider the potential effects that negative events can have on a business. Another way to represent this idea is:

**Likelihood × Impact = Risk**

For example, you risk being late when you drive a car to work. This negative event is more likely if you get a flat tire along the way. The impact could be serious, like losing your job. All these factors influence how you approach commuting to work every day. The same is true for how businesses handle security risks.

In general, risk is calculated to help:

- Prevent costly and disruptive events
- Identify improvements that can be made to systems and processes
- Determine which risks can be tolerated
- Prioritize the critical assets that require attention

The business impact of a negative event depends on the asset and the situation. A security professional will focus on the likelihood side of the equation by dealing with factors that increase the odds of a problem.

### Risk Factors

There are two broad risk factors in security:

- Threats
- Vulnerabilities

The risk of an asset being harmed or damaged depends greatly on whether a threat takes advantage of vulnerabilities.

For example, in the risk of being late to work, a threat would be a nail puncturing your tire, since tires are vulnerable to running over sharp objects. In security planning, you would want to reduce the likelihood of this risk by driving on a clean road.

### Categories of Threat

Threats are circumstances or events that can negatively impact assets.

They are commonly categorized as:

- Intentional
- Unintentional

Examples:

- An **intentional threat** might be a malicious hacker who gains access to sensitive information by targeting a misconfigured application.
- An **unintentional threat** might be an employee who holds the door open for an unknown person and grants them access to a restricted area.

Either one can cause an event that must be responded to.

### Categories of Vulnerability

Vulnerabilities are weaknesses that can be exploited by threats.

They are commonly grouped into two categories:

- Technical
- Human

Examples:

- A **technical vulnerability** can be misconfigured software that might give an unauthorized person access to important data.
- A **human vulnerability** can be a forgetful employee who loses their access card in a parking lot.

Either one can lead to risk.

### Key Takeaways

- Risk, threat, and vulnerability have very specific meanings in security.
- Knowing the relationship between them helps build a strong foundation as a security analyst.
- This knowledge helps demonstrate working knowledge of the field and signals that you are part of the global security community.

---

## Asset Management and Classification

Asset management is the process of tracking assets and the risks that affect them.

The idea behind this process is simple: **you can only protect what you know you have**.

Previously, you learned that identifying, tracking, and classifying assets are all important parts of asset management.

### Why Asset Management Matters

Keeping assets safe requires a workable system that helps businesses operate smoothly. Setting these systems up requires detailed knowledge of the assets in an environment.

For example, a bank needs to have money available each day to serve its customers. Equipment, devices, and processes need to be in place to ensure that money is available and secure from unauthorized access.

Organizations protect a variety of different assets, including:

- Digital assets such as customer data or financial records
- Information systems that process data, like networks or software
- Physical assets such as facilities, equipment, or supplies
- Intangible assets such as brand reputation or intellectual property

Regardless of its type, every asset should be classified and accounted for.

**Asset classification** is the practice of labeling assets based on sensitivity and importance to an organization.

Determining sensitivity and importance typically requires knowing:

- What you have
- Where it is
- Who owns it
- How important it is

An organization classifies its assets based on these characteristics to determine the sensitivity and value of an asset.

### Common Asset Classifications

Asset classification helps organizations implement an effective risk management strategy. It also helps them:

- Prioritize security resources
- Reduce IT costs
- Stay in compliance with legal regulations

The most common classification scheme is:

- Restricted
- Confidential
- Internal-only
- Public

#### Restricted

Restricted is the highest level. This category is reserved for incredibly sensitive assets, like need-to-know information.

#### Confidential

Confidential refers to assets whose disclosure may lead to a significant negative impact on an organization.

#### Internal-only

Internal-only describes assets that are available to employees and business partners.

#### Public

Public is the lowest level of classification. These assets have no negative consequences to the organization if they are released.

How this scheme is applied depends greatly on the characteristics of an asset. Identifying an asset’s owner is sometimes the most complicated characteristic to determine.

**Note:** Although many organizations adopt this classification scheme, there can be variability at the highest levels. For example, government organizations label their most sensitive assets as confidential instead of restricted.

### Challenges of Classifying Information

Identifying the owner of some assets is straightforward, like the owner of a building. Other assets can be trickier to identify, especially information.

For example, a business might issue a laptop to an employee so they can work remotely. You might assume the business is the asset owner. But what if the employee uses the laptop for personal matters, like storing their photos?

Ownership is just one characteristic that makes classifying information a challenge. Another concern is that information can have multiple classification values at the same time.

For example, consider a letter addressed to you in the mail. The letter contains:

- Public information that is okay to share, like your name
- Confidential information you would rather only be available to certain people, like your address

You will learn more about how these challenges are addressed as you continue through the program.

### Key Takeaways

- Every business is different and will have specific requirements when devising a security strategy.
- Knowing why and how businesses classify their assets is an important skill for a security professional.
- Information is one of the most important assets in the world.
- As a cybersecurity professional, you will be closely involved with protecting information from damage, disclosure, and misuse.
- Recognizing the challenges businesses face when classifying information is key to helping them solve their security needs.

---

## Cloud Computing and Cloud Security

One of the most significant technology developments this century has been the emergence of cloud computing.

The United Kingdom's National Cyber Security Centre defines cloud computing as:

> An on-demand, massively scalable service, hosted on shared infrastructure, accessible via the internet.

Earlier, you learned that most information is in the form of data, which is in a constant state of change. In recent years, businesses started moving their data to the cloud. The adoption of cloud-based services has complicated how information is kept safe online.

### Soaring Into the Cloud

Starting an online business used to be complicated and costly. In years past, companies had to build and maintain their own internal solutions to operate in the digital marketplace. Now, it is much easier for anyone to participate because of the cloud.

Cloud technologies have drastically changed how businesses operate online. These tools allow companies to scale and adapt quickly while also lowering costs. Despite these benefits, the shift to cloud-based services has introduced new cybersecurity challenges that put assets at risk.

### Cloud-Based Services

Cloud-based services refers to a variety of on-demand or web-based business solutions.

Depending on a company’s needs and budget, services can range from:

- Website hosting
- Application development environments
- Entire back-end infrastructure

There are three main categories of cloud-based services:

- Software as a service (SaaS)
- Platform as a service (PaaS)
- Infrastructure as a service (IaaS)

#### Software as a Service (SaaS)

SaaS refers to front-end applications that users access via a web browser.

Service providers host, manage, and maintain all of the back-end systems for those applications.

Examples include:

- Gmail
- Slack
- Zoom

#### Platform as a Service (PaaS)

PaaS refers to back-end application development tools that clients can access online.

Developers use these resources to write code and build, manage, and deploy their own apps. Meanwhile, the cloud service providers host and maintain the back-end hardware and software that the apps use to operate.

Examples include:

- Google App Engine
- Heroku
- VMware Cloud Foundry

#### Infrastructure as a Service (IaaS)

IaaS customers are given remote access to a range of back-end systems hosted by the cloud service provider.

This includes:

- Data processing servers
- Storage
- Networking resources
- More

Resources are commonly licensed as needed, making this a cost-effective alternative to buying and maintaining on-premises infrastructure.

Cloud-based services allow companies to connect with their customers, employees, and business partners over the internet.

Some of the largest organizations in the world offer cloud-based services, including:

- Google Cloud Platform
- Microsoft Azure

### Cloud Security

Shifting applications and infrastructure to the cloud can make it easier to operate an online business. It can also complicate keeping data private and safe.

Cloud security is a growing subfield of cybersecurity that focuses specifically on the protection of data, applications, and infrastructure in the cloud.

In a traditional model, organizations had their entire IT infrastructure on premises. Protecting those systems was entirely up to the internal security team. These responsibilities are not so clearly defined when part or all of an operational environment is in the cloud.

For example, a PaaS client pays to access the resources they need to build their applications. It is reasonable to expect them to be responsible for securing the apps they build. On the other hand, maintaining the security of the servers they are accessing should belong to the cloud service provider because there are other clients using the same systems.

In cloud security, this is known as the **shared responsibility model**.

Clients are commonly responsible for securing anything directly within their control:

- Identity and access management
- Resource configuration
- Data handling

**Note:** The amount of responsibility delegated to a service provider varies depending on the service being used: SaaS, PaaS, and IaaS.

### Cloud Security Challenges

All service providers do their best to deliver secure products to their customers. Much of their success depends on preventing breaches and protecting sensitive information.

However, since data is stored in the cloud and accessed over the internet, several challenges arise:

- **Misconfiguration** is one of the biggest concerns. Customers are responsible for configuring their own security environment. Often, they use out-of-the-box configurations that fail to address their specific security objectives.
- Cloud-native breaches are more likely to occur due to misconfigured services.
- Monitoring access might be difficult depending on the client and level of service.
- Meeting regulatory standards is also a concern, particularly in industries required by law to follow specific requirements such as HIPAA, PCI DSS, and GDPR.

As more businesses adopt cloud-based services, there is a growing need for cloud security professionals.

Burning Glass ranks cloud security among the most in-demand skills in cybersecurity.

### Key Takeaways

- Much of the global marketplace has shifted to cloud-based services.
- Cloud technology is still relatively new, creating new security models and a range of security challenges.
- Being familiar with the cloud and the different services available is an important step toward supporting organizations in protecting information online.

### Resources for More Information

Cloud security is one of the fastest-growing subfields of cybersecurity. Resources available online include:

- The U.K.’s National Cyber Security Centre, which has a guide for choosing, using, and deploying cloud services securely based on the shared responsibility model
- The Cloud Security Alliance, which creates secure cloud environments and offers cloud security research, certification, and products to paid members
- CompTIA Cloud+, a certificate program designed to teach foundational skills needed to become a cloud security specialist

---

## The NIST Cybersecurity Framework (CSF)

Organizations often face an overwhelming amount of risk. Developing a security plan from the beginning that addresses all risk can be challenging. This makes security frameworks a useful option.

Previously, you learned about the NIST Cybersecurity Framework (CSF). A major benefit of the CSF is that it is flexible and can be applied to any industry.

### Origins of the Framework

Originally released in 2014, NIST developed the Cybersecurity Framework to protect critical infrastructure in the United States.

NIST was selected because it is an unbiased source of scientific data and practices. NIST eventually adapted the CSF to fit the needs of businesses in the public and private sector.

The goal was to make the framework more flexible and easier to adopt for small businesses or anyone else that might lack the resources to develop their own security plans.

### Components of the CSF

The framework consists of three main components:

- Core
- Tiers
- Profiles

#### Core

The CSF core is a set of desired cybersecurity outcomes that help organizations customize their security plan.

It consists of six functions:

- Identify
- Protect
- Detect
- Respond
- Recover
- Govern

These functions are used as an informative reference to help organizations identify their most important assets, protect those assets with appropriate safeguards, understand ways to detect attacks, and develop response and recovery plans if an attack happens.

Previously, the core consisted of just five functions. Govern was added in February 2024 to emphasize the importance of leadership and decision-making in managing cybersecurity risks.

#### Tiers

The CSF tiers are a way of measuring the sophistication of an organization’s cybersecurity program.

- They are measured on a scale of 1 to 4.
- Tier 1 is the lowest score, indicating that a limited set of security controls have been implemented.
- Tiers are used to assess an organization’s security posture and identify areas for improvement.

#### Profiles

The CSF profiles are pre-made templates of the NIST CSF that are developed by a team of industry experts.

They are tailored to address the specific risks of an organization or industry.

They are used to help organizations:

- Develop a baseline for cybersecurity plans
- Compare their current cybersecurity posture to a specific industry standard

**Note:** The core, tiers, and profiles were designed to help any business improve security operations. Although there are only three components, the entire framework includes a complex system of subcategories and processes.

### Implementing the CSF

Compliance is the process of adhering to internal standards and external regulations.

In other words, compliance is a way of measuring how well an organization is protecting their assets.

The NIST CSF is a voluntary framework that consists of standards, guidelines, and best practices to manage cybersecurity risk. Organizations may choose to use the CSF to achieve compliance with a variety of regulations.

**Note:** Regulations are rules that must be followed, while frameworks are resources you can choose to use.

Since its creation, many businesses have used the NIST CSF. However, the CSF can be challenging to implement due to its high level of detail.

It can also be hard to determine where the framework fits in. Some businesses already have security plans, making it unclear how CSF can help. Other businesses may be in the early stages of building plans and need a place to start.

The U.S. Cybersecurity and Infrastructure Security Agency (CISA) provides detailed guidance any organization can use to implement the CSF. Their recommendations include:

- Create a current profile of the security operations and outline the specific needs of your business
- Perform a risk assessment to identify which current operations are meeting business and regulatory standards
- Analyze and prioritize existing gaps in security operations that place the business assets at risk
- Implement a plan of action to achieve the organization’s goals and objectives

**Pro Tip:** Always consider current risk, threat, and vulnerability trends when using the NIST CSF.

You can learn more about implementing the CSF in a CISA report that outlines how the framework was applied in the commercial facilities sector.

### Industries Embracing the CSF

The NIST CSF has continued to evolve since its introduction in 2014. Its design is influenced by the standards and best practices of some of the largest companies in the world.

A benefit of the framework is that it aligns with the security practices of many organizations across the global economy. It also helps with regulatory compliance that might be shared by business partners.

### Key Takeaways

- The NIST CSF is a flexible resource that organizations may choose to use to assess and improve their security posture.
- It is a useful framework that combines security best practices from industries around the world.
- Implementing the CSF can be challenging for any organization.
- The CSF can help businesses meet regulatory compliance requirements to avoid financial and reputational risks.

---

## Terms and Definitions — Course 5, Module 1

| Term | Definition |
|---|---|
| Asset | An item perceived as having value to an organization |
| Asset classification | The practice of labeling assets based on sensitivity and importance to an organization |
| Asset inventory | A catalog of assets that need to be protected |
| Asset management | The process of tracking assets and the risks that affect them |
| Compliance | The process of adhering to internal standards and external regulations |
| Data | Information that is translated, processed, or stored by a computer |
| Data at rest | Data not currently being accessed |
| Data in transit | Data traveling from one point to another |
| Data in use | Data being accessed by one or more users |
| Information security (InfoSec) | The practice of keeping data in all states away from unauthorized users |
| National Institute of Standards and Technology (NIST) Cybersecurity Framework (CSF) | A voluntary framework that consists of standards, guidelines, and best practices to manage cybersecurity risk |
| Policy | A set of rules that reduce risk and protect information |
| Procedures | Step-by-step instructions to perform a specific security task |
| Regulations | Rules set by a government or other authority to control the way something is done |
| Risk | Anything that can impact confidentiality, integrity, or availability of an asset |
| Standards | References that inform how to set policies |
| Threat | Any circumstance or event that can negatively impact assets |
| Vulnerability | A weakness that can be exploited by a threat |
