# Course 5 — Module 4

## Table of Contents

- [Social Engineering](#social-engineering)
- [Phishing](#phishing)
- [Malware](#malware)
- [SQL Injection](#sql-injection)
- [Threat Modeling](#threat-modeling)
- [Terms and Definitions](#terms-and-definitions-course-5-module-4)

---

## Social Engineering

Social engineering attacks are a popular choice among threat actors because it is often easier to trick people into providing access, information, or money than it is to exploit a software or network vulnerability.

Social engineering is a manipulation technique that exploits human error to gain private information, access, or valuables. It is an umbrella term that can apply to a broad range of attacks. Each technique is designed to capitalize on the trusting nature of people and their willingness to help.

### Social Engineering Risks

Social engineering is a form of deception that takes advantage of the way people think. It preys on natural feelings like:

- Curiosity
- Generosity
- Excitement

Threat actors turn those feelings against their targets by affecting their better judgment.

A high-profile example was the Twitter Hack of 2020. In that incident, hackers made phone calls to Twitter employees pretending to be from the IT department. Using this basic scam, they gained access to internal tools and took over accounts of high-profile users.

These attacks are serious because they do not require sophisticated computer skills to perform. Defending against them requires a multi-layered approach that combines technological controls with user awareness.

### Signs of an Attack

Recognizing the signs of social engineering is key to reducing the likelihood of a successful attack.

Common types of social engineering include:

#### Baiting
A tactic that tempts people into compromising their security.

Example:

- USB baiting, where someone finds an infected USB drive and plugs it into their device.

#### Phishing
The use of digital communications to trick people into revealing sensitive data or deploying malicious software.

#### Quid Pro Quo
A type of baiting used to trick someone into believing they will be rewarded in return for sharing access, information, or money.

Example:

- An attacker impersonates a loan officer and offers a lower credit card interest rate in exchange for account details.

#### Tailgating
A tactic in which unauthorized people follow an authorized person into a restricted area.

This is also sometimes called piggybacking.

#### Watering Hole
A type of attack when a threat actor compromises a website frequently visited by a specific group of users.

Example:

- The Holy Water attack of 2020 infected various religious, charity, and volunteer websites.

### Encouraging Caution

Security awareness training should focus on three main areas:

- Stay alert for suspicious communications and unknown people, especially in email.
  - Look for spelling errors.
  - Double-check the sender name and email address.
- Be cautious about sharing information, especially over social media.
- Control curiosity when something seems too good to be true.
  - Be careful with attachments and links in emails and advertisements.

**Pro tip:** Firewalls, multi-factor authentication (MFA), block lists, email filtering, and similar technologies add more layers of defense if someone makes a mistake.

Security training should ideally extend beyond employees to include customers. Security analysts also play an important role in promoting safe practices and documenting best practices for others to follow.

### Key Takeaways

- Social engineering exploits trust and human judgment.
- Basic manipulation can be enough to succeed.
- Recognizing suspicious behavior and using layered controls can reduce risk.

---

## Phishing

Phishing is one of the most common types of social engineering. It uses digital communications to trick people into revealing sensitive data or deploying malicious software.

Sometimes phishing messages appear to come from trusted people or businesses, leading recipients to act against their better judgment.

### The Origins of Phishing

Phishing has existed since the early days of the internet and can be traced back to the 1990s.

As the internet became more accessible, malicious actors realized it gave them anonymity to commit crimes.

One early phishing target was AOL Instant Messenger (AIM). Users received emails asking them to verify accounts or provide billing information. These messages were sent by malicious actors pretending to be service providers.

This was one of the first examples of **mass phishing**, which sends malicious emails to a large number of people in hopes of tricking someone.

Attackers used official logos, colors, and fonts to make the emails seem legitimate.

They used stolen information to create fraudulent AOL accounts for other crimes, and AOL eventually added warnings about phishing on its platforms.

### How Phishing Has Evolved

As e-commerce and online payment systems became popular in the early 2000s, phishing evolved into new forms.

Common phishing types include:

#### Email Phishing
An attack sent via email in which threat actors pretend to be trusted people or entities.

#### Smishing
A type of phishing that uses SMS text messages. This includes services like iMessage, WhatsApp, and other phone-based messaging platforms.

#### Vishing
The use of voice calls or voice messages to trick targets into providing personal information over the phone.

#### Spear Phishing
A subset of email phishing in which specific people are targeted, such as the accountants of a small business.

#### Whaling
A category of spear phishing aimed at high-ranking executives.

Email phishing remains the most common type of phishing. In the past, attackers used it to steal credentials and credit card data. Later, it became a popular method for infecting systems and networks with malware.

In the late 2000s and early 2010s, attackers also created fraudulent websites that resembled businesses like eBay and PayPal.

### Recent Trends

Starting in the 2010s, attackers moved away from mass phishing toward **targeted phishing**.

Targeted phishing uses highly customized methods to create a strong sense of familiarity.

One example is **angler phishing**, which impersonates customer service representatives on social media.

Attackers may:

- Intercept complaints on message boards or comment sections
- Contact angry customers through social media
- Use fake accounts that look like real businesses
- Trick victims into sharing sensitive information by promising to fix a problem

### Key Takeaways

- Phishing tactics have become more sophisticated over time.
- Email phishing remains effective and profitable for attackers.
- There is no perfect technological solution that prevents phishing entirely.
- Awareness training is an important way to reduce the damage from phishing attacks.

---

## Malware

Previously, you learned that malware is software designed to harm devices or networks. Malware has developed into a variety of strains over time.

### Virus

A virus is malicious code written to interfere with computer operations and cause damage to data and software.

- It must be installed by the target user before it can spread.
- Common spread method: phishing campaigns with malicious links or attachments.

### Worm

A worm is malware that can duplicate and spread itself across systems on its own.

- Like a virus, it must be installed by the target user.
- It can also spread through tactics like malicious email.
- Attackers sometimes target devices, drives, or files with shared network access.

A well-known example is the Blaster worm, also called Lovesan, Lovsan, or MSBlast. In the early 2000s, it spread on Windows XP and Windows 2000 systems and caused devices to repeatedly shut down and restart. It spread to hundreds of thousands of users worldwide.

**Note:** Worms were very popular in the mid-2000s but are less frequently used now.

### Trojan

A trojan, also called a Trojan horse, is malware that looks like a legitimate file or program.

- Attackers deliver it hidden in file and application downloads.
- Users believe they are downloading something harmless, but they are actually infecting their own device.

Trojans can be used to spy on users, grant access to other devices, and more.

### Adware

Advertising-supported software (adware) is sometimes used to display digital advertisements in applications.

- Developers may use adware to lower production costs or make products free.
- Legitimate adware monetizes through ads.

Malicious adware is a potentially unwanted application (PUA).

A PUA may:

- Display ads
- Cause device slowdown
- Install other software

### Spyware

Spyware is malware used to gather and sell information without consent.

- It is also considered a PUA.
- It is commonly hidden in bundleware, additional software packaged with other applications.

### Scareware

Scareware is another type of PUA.

- It frightens users into infecting their own device.
- It often uses fake warnings that appear to come from legitimate companies.
- Email and pop-ups are common delivery methods.

### Fileless Malware

Fileless malware does not need to be installed by the user.

- It uses legitimate programs already installed on the computer.
- It resides in memory and never touches the hard drive.
- It can hide within the operating system or trusted applications.

**Pro tip:** Fileless malware is detected by performing memory analysis, which requires operating system experience.

### Rootkits

A rootkit is malware that provides remote, administrative access to a computer.

- It is often used to open a backdoor into systems.
- Attackers use it to install other malware or conduct network attacks.

Rootkits are often spread by a **dropper** and a **loader**.

#### Dropper
Malware that comes packed with malicious code and is delivered and installed onto a target system.

#### Loader
Malware that downloads strains of malicious code from an external source and installs them onto a target system.

### Botnet

A botnet, short for robot network, is a collection of infected computers controlled by a single threat actor known as the bot-herder.

- Viruses, worms, and trojans are often used to spread the initial infection.
- The attacker may use file sharing, email, or social media application protocols to grow the botnet.
- The infected computer, or bot, reports information back to the bot-herder.

### Ransomware

Ransomware is a malicious attack where threat actors encrypt an organization’s data and demand payment to restore access.

An example is the WannaCry attack, which encrypted victim computers until a ransom payment in cryptocurrency was paid.

### Key Takeaways

- Malware comes in many forms.
- Different malware types spread in different ways.
- Recognizing malware types and their delivery methods helps defend against attacks.
- Malware analysis is an important cybersecurity specialization.

---

## SQL Injection

Previously, you learned that Structured Query Language (SQL) is a programming language used to create, interact with, and request information from a database.

SQL injection is a common attack vector used to gain unauthorized access to web applications.

Due to SQL’s popularity with developers, SQL injections appear regularly in the OWASP Top 10 because many developers focus on making applications work correctly rather than protecting them from injection.

### SQL Queries

A database is an organized collection of information or data in one place. In SQL, database information is organized in tables.

SQL queries are used to:

- Retrieve information
- Insert information
- Update information
- Delete information

A SQL query is a request for data from a database.

Queries are usually initiated where users can input information into an application or website, such as:

- Login forms
- Search bars
- Comment boxes

A SQL injection occurs when an attacker exploits input fields that are not programmed to filter out unwanted text.

SQL injections can be used to:

- Manipulate databases
- Steal sensitive data
- Take control of vulnerable applications

### SQL Injection Categories

There are three main categories of SQL injection:

- In-band
- Out-of-band
- Inferential

#### In-band SQL Injection

In-band, or classic, SQL injection is the most common type.

It uses the same communication channel to launch the attack and gather the results.

Example:

- A vulnerable search box returns sensitive information like user passwords directly in the search results.

#### Out-of-band SQL Injection

An out-of-band injection uses a different communication channel to launch the attack and gather the results.

This is uncommon and only works when certain features are enabled on the target server.

#### Inferential SQL Injection

Inferential SQL injection occurs when an attacker cannot directly see the results of the attack.

Instead, the attacker interprets the results by analyzing the behavior of the system.

Example:

- A login form returns an error message.
- The attacker uses the error to infer the database structure.
- They then craft more attacks to gain access to data or control the system.

### Injection Prevention

A key to preventing SQL injection is to escape user inputs so users cannot insert unexpected code.

Ways to escape input include:

- Prepared statements
- Input sanitization
- Input validation

#### Prepared Statements
A coding technique that executes SQL statements before passing them to a database.

#### Input Sanitization
Programming that removes user input that could be interpreted as code.

#### Input Validation
Programming that ensures user input meets a system’s expectations.

Using a combination of these techniques helps prevent SQL injection attacks.

### Key Takeaways

- SQL injections are common because SQL is widely used.
- They happen when user input is not properly filtered.
- Developers and security professionals should work together to prevent them.
- OWASP provides resources for investigating SQL injection vulnerabilities.

---

## Threat Modeling

Threat modeling is the process of identifying assets, their vulnerabilities, and how each is exposed to threats.

It is a strategic approach that combines:

- Vulnerability management
- Threat analysis
- Incident response

Threat modeling is often associated with application development, but it can be used more broadly to reduce risks to any system or business process.

### Why Application Security Matters

Applications are essential to many organizations.

Examples:

- Web-based applications connect customers, partners, and other customers worldwide.
- Mobile applications have changed how people access the digital world.

Applications process large volumes of data, so securing them is key to reducing risk.

For example, if an application uses Java-based logging libraries with the Log4Shell vulnerability (CVE-2021-44228) and is not patched, attackers may be able to achieve remote code execution and gain access from anywhere in the world.

### Defending the Application Layer

Defending the application layer requires proper testing to uncover weaknesses.

Threat modeling is one of the primary ways to ensure an application meets security requirements.

A DevSecOps team, meaning development, security, and operations, usually performs these analyses.

A typical threat modeling process follows this cycle:

1. Define the scope
2. Identify threats
3. Characterize the environment
4. Analyze threats
5. Mitigate risks
6. Evaluate findings

Threat modeling should ideally be performed before, during, and after an application is developed.

It should also be incorporated at every stage of the software development lifecycle (SDLC).

### Common Frameworks

Common threat modeling frameworks include:

- STRIDE
- PASTA
- Trike
- VAST

#### STRIDE
A Microsoft-developed framework used to identify vulnerabilities in six specific attack vectors:

- Spoofing
- Tampering
- Repudiation
- Information disclosure
- Denial of service
- Elevation of privilege

#### PASTA
The Process of Attack Simulation and Threat Analysis is a risk-centric framework developed by two OWASP leaders and supported by VerSprite.

Its goal is to discover evidence of viable threats and represent the information as a model.

PASTA uses a seven-stage process and can incorporate artifacts like vulnerability assessment reports.

#### Trike
An open-source methodology and tool that takes a security-centric approach to threat modeling.

It focuses on:

- Security permissions
- Application use cases
- Privilege models
- Other elements that support a secure environment

#### VAST
The Visual, Agile, and Simple Threat Modeling framework is part of the ThreatModeler automated platform.

It is often used to automate and streamline threat modeling assessments.

### Participating in Threat Modeling

Threat modeling is often performed by experienced security professionals, but it is almost never done alone.

Important questions to ask include:

- What are we working on?
- What kinds of things can go wrong?
- What are we doing about it?
- Have we addressed everything?
- Did we do a good job?

It takes time and practice to work with data flow diagrams and attack trees. However, anyone can learn to be an effective threat modeler.

### Key Takeaways

- Threat modeling helps determine whether security controls are in place to protect data privacy.
- It is a key part of securing software applications.
- Even a security analyst with little experience can contribute by asking the right questions and thinking critically about data handling.

---

## Terms and Definitions — Course 5, Module 4

| Term | Definition |
|---|---|
| Angler phishing | A technique where attackers impersonate customer service representatives on social media |
| Advanced persistent threat (APT) | Instances when a threat actor maintains unauthorized access to a system for an extended period of time |
| Adware | A type of legitimate software that is sometimes used to display digital advertisements in applications |
| Attack tree | A diagram that maps threats to assets |
| Baiting | A social engineering tactic that tempts people into compromising their security |
| Botnet | A collection of computers infected by malware that are under the control of a single threat actor, known as the bot-herder |
| Cross-site scripting (XSS) | An injection attack that inserts code into a vulnerable website or web application |
| Cryptojacking | A form of malware that installs software to illegally mine cryptocurrencies |
| DOM-based XSS attack | An instance when malicious script exists in the webpage a browser loads |
| Dropper | A type of malware that comes packed with malicious code which is delivered and installed onto a target system |
| Fileless malware | Malware that does not need to be installed by the user because it uses legitimate programs that are already installed to infect a computer |
| Hacker | Any person or group who uses computers to gain unauthorized access to data |
| Identity and access management (IAM) | A collection of processes and technologies that helps organizations manage digital identities in their environment |
| Injection attack | Malicious code inserted into a vulnerable application |
| Input validation | Programming that validates inputs from users and other programs |
| Intrusion detection system (IDS) | An application that monitors system activity and alerts on possible intrusions |
| Loader | A type of malware that downloads strains of malicious code from an external source and installs them onto a target system |
| Malware | Software designed to harm devices or networks |
| Process of Attack Simulation and Threat Analysis (PASTA) | A popular threat modeling framework that’s used across many industries |
| Phishing | The use of digital communications to trick people into revealing sensitive data or deploying malicious software |
| Phishing kit | A collection of software tools needed to launch a phishing campaign |
| Prepared statement | A coding technique that executes SQL statements before passing them onto the database |
| Potentially unwanted application (PUA) | A type of unwanted software that is bundled in with legitimate programs which might display ads, cause device slowdown, or install other software |
| Quid pro quo | A type of baiting used to trick someone into believing that they’ll be rewarded in return for sharing access, information, or money |
| Ransomware | Type of malicious attack where attackers encrypt an organization’s data and demand payment to restore access |
| Reflected XSS attack | An instance when malicious script is sent to a server and activated during the server’s response |
| Rootkit | Malware that provides remote, administrative access to a computer |
| Scareware | Malware that employs tactics to frighten users into infecting their device |
| Smishing | The use of text messages to trick users to obtain sensitive information or to impersonate a known source |
| Social engineering | A manipulation technique that exploits human error to gain private information, access, or valuables |
| Spear phishing | A malicious email attack targeting a specific user or group of users, appearing to originate from a trusted source |
| Spyware | Malware that’s used to gather and sell information without consent |
| SQL (Structured Query Language) | A programming language used to create, interact with, and request information from a database |
| SQL injection | An attack that executes unexpected queries on a database |
| Stored XSS attack | An instance when malicious script is injected directly on the server |
| Tailgating | A social engineering tactic in which unauthorized people follow an authorized person into a restricted area |
| Threat | Any circumstance or event that can negatively impact assets |
| Threat actor | Any person or group who presents a security risk |
| Threat modeling | The process of identifying assets, their vulnerabilities, and how each is exposed to threats |
| Trojan horse | Malware that looks like a legitimate file or program |
| Vishing | The exploitation of electronic voice communication to obtain sensitive information or to impersonate a known source |
| Watering hole attack | A type of attack when a threat actor compromises a website frequently visited by a specific group of users |
| Whaling | A category of spear phishing attempts that are aimed at high-ranking executives in an organization |
| Web-based exploits | Malicious code or behavior that’s used to take advantage of coding flaws in a web application |
