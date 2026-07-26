# Course 4, Module 1

## Common Operating Systems

Operating systems useful to know in the security industry:

- Windows
- macOS
- Linux
- ChromeOS
- Android
- iOS

### Windows and macOS

Windows and macOS are both common operating systems used in personal and enterprise computers.

| Operating System | Introduced | Source |
|---|---:|---|
| Windows | 1985 | Closed source |
| macOS | 1984 | Partially open source |

- **Windows** is a closed-source operating system. Its source code is not shared freely with the public.
- **macOS** is partially open source. It has some open-source components, such as the macOS kernel, and some closed-source components.

### Linux

- First version released in 1991.
- Other major releases followed in the early 1990s.
- Completely open-source operating system.
- Anyone can access Linux and its source code.
- Its open-source nature allows developers in the Linux community to collaborate.
- Particularly important to the security industry.
- Some Linux distributions are specifically designed for security.

### ChromeOS

- Launched in 2011.
- Partially open source.
- Derived from Chromium OS, which is completely open source.
- Frequently used in the education field.

### Android and iOS

Android and iOS are mobile operating systems. Mobile operating systems are typically used in devices such as phones, tablets, and watches.

| Operating System | Introduced | Source |
|---|---:|---|
| Android | 2008 | Open source |
| iOS | 2007 | Partially open source |

---

## Operating Systems and Vulnerabilities

Security issues are inevitable with all operating systems.

An important part of protecting an operating system is keeping the system and all of its components up to date.

### Legacy Operating Systems

A **legacy operating system** is an operating system that is outdated but still being used.

Some organizations continue to use legacy operating systems because software they rely on is not compatible with newer operating systems.

This can be more common in industries that use equipment requiring **embedded software**.

**Embedded software** is software that is placed inside components of equipment.

### Risks of Legacy Operating Systems

Legacy operating systems can be vulnerable to security issues because they are no longer supported or updated. This means they may be vulnerable to new threats.

Keeping an operating system up to date is one key way to help the system stay secure.

Because it can be difficult to keep all systems updated at all times, security analysts should be knowledgeable about legacy operating systems and the risks they can create.

### Other Vulnerabilities

Even when operating systems are kept up to date, they can still become vulnerable to attack.

- **Microsoft Security Response Center (MSRC):** A list of known vulnerabilities affecting Microsoft products and services
- **Apple Security Updates:** A list of security updates and information for Apple operating systems, including macOS and iOS, and other products
- **Common Vulnerabilities and Exposures (CVE) Report for Ubuntu:** A list of known vulnerabilities affecting Ubuntu, which is a specific distribution of Linux
- **Google Cloud Security Bulletin:** A list of known vulnerabilities affecting Google Cloud products and services

### Key Takeaways

- Windows, macOS, Linux, ChromeOS, Android, and iOS are all commonly used operating systems.
- Security analysts should be aware of vulnerabilities that affect operating systems.
- It is especially important for security analysts to be familiar with legacy operating systems.
- Legacy operating systems are outdated systems that are still being used.
- Keeping an operating system up to date is one key way to help the system stay secure.

---

## How an Operating System Works

Operating systems are a critical component of a computer. They make connections between applications and hardware to allow users to perform tasks.

### Booting the Computer

When you boot, or turn on, your computer, either a BIOS or UEFI microchip is activated.

#### BIOS

**Basic Input/Output System (BIOS)**

- A microchip that contains loading instructions for the computer.
- Prevalent in older systems.
- Was the standard chip until 2007.

#### UEFI

**Unified Extensible Firmware Interface (UEFI)**

- A microchip that contains loading instructions for the computer.
- Replaces BIOS on more modern systems.
- Most new computers include a UEFI chip.
- Provides enhanced security features.

#### BIOS and UEFI

- BIOS and UEFI both perform the same function for booting the computer.
- BIOS was the standard chip until 2007, when UEFI chips increased in use.
- The BIOS or UEFI microchips contain loading instructions for the computer to follow.
- One example of a loading instruction is to verify the health of the computer’s hardware.

The last instruction from the BIOS or UEFI activates the **bootloader**.

**Bootloader:** A software program that boots the operating system.

Once the operating system has finished booting, the computer is ready for use.

#### Boot Process

    Computer turned on
            ↓
    BIOS / UEFI activated
            ↓
    Loading instructions followed
            ↓
    Hardware health verified
            ↓
    Bootloader activated
            ↓
    Operating system boots
            ↓
    Computer ready for use

---

## Completing a Task

Once a computer has gone through the booting process, completing a task on a computer is a four-part process.

    User
      ↓
    Application
      ↓
    Operating System
      ↓
    Hardware

After the hardware does the work, it sends the output back through the operating system to the application so that it can display the results to the user.

    User
      ↓
    Application
      ↓
    Operating System
      ↓
    Hardware
      ↓
    Operating System
      ↓
    Application
      ↓
    User

### 1. User

The user initiates the process by having something they want to accomplish on the computer.

Examples:

- Accessing a reading
- Calculating a number
- Saving a file

### 2. Application

The application is the software program that users interact with to complete a task.

Examples:

- Calculator application → calculate something
- Word processing application → write a report

### 3. Operating System

The operating system receives the user’s request from the application.

The operating system’s job is to:

- Interpret the request
- Direct its flow
- Send it to applicable components of the hardware

### 4. Hardware

The hardware is where all processing is done to complete the tasks initiated by the user.

Examples:

- CPU figures out the answer when a user wants to calculate a number
- Hard drive handles saving a file when a user wants to save a file

After the hardware completes the work, it sends the output back through the operating system to the application so it can display the results to the user.

---

## The OS at Work Behind the Scenes

Important work happens inside a computer that users do not experience directly. This work involves the operating system.

### Restaurant Analogy

The process of using an operating system is similar to ordering at a restaurant.

At a restaurant:

- You place an order.
- The kitchen prepares the food.
- You receive your food.
- You do not see what is happening in the kitchen.

The computer process is similar.

| Computer | Restaurant |
|---|---|
| Application | Ordering food |
| Operating system | Kitchen |
| Hardware | Food preparation |
| Output | Food received |

Ordering food is similar to using an application on a computer.

When ordering food, you make a specific request such as:

> A small soup, very hot.

When using an application, you also make specific requests such as:

> Print three double-sided copies of this document.

The food you receive can be compared to what happens when the hardware sends output.

The kitchen is like the operating system:

- You do not know what happens in the kitchen.
- The kitchen is critical in interpreting the request.
- The kitchen ensures you receive what you ordered.

Similarly, the work of the OS is not directly transparent to you, but it is critical in completing your tasks.

---

## Example: Downloading a File From an Internet Browser

Operating systems, applications, and hardware work together when downloading a file from an internet browser.

### Process

1. The user decides they want to download a file that they found online.
2. The user clicks a download button near the file in the internet browser application.
3. The internet browser communicates this action to the OS.
4. The OS sends the request to download the file to the appropriate hardware for processing.
5. The hardware begins downloading the file.
6. The OS sends this information to the internet browser application.
7. The internet browser informs the user when the file has been downloaded.

### Key Takeaway

Although it operates in the background, the operating system is an essential part of the process of using a computer. The operating system connects applications and hardware to allow users to complete a task.

---

## Virtual Machines and Virtualization

Operating systems can run on virtual machines.

### What Is a Virtual Machine?

A **virtual machine (VM)** is a virtual version of a physical computer.

Virtual machines are one example of **virtualization**.

### Virtualization

**Virtualization** is the process of using software to create virtual representations of physical machines.

The term “virtual” refers to machines that:

- Do not exist physically
- Operate like physical machines because their software simulates physical hardware

Virtual systems:

- Do not use dedicated physical hardware
- Use software-defined versions of the physical hardware
- Are essentially code

A single virtual machine has:

- A virtual CPU
- Virtual storage
- Other virtual hardware

### Multiple Virtual Machines

You can run multiple virtual machines using the physical hardware of a single computer.

This involves dividing the resources of the host computer to be shared across all physical and virtual components.

**Example: RAM**

**Random Access Memory (RAM)** is a hardware component used for short-term memory.

If a computer has 16 GB of RAM, it can host three virtual machines so that the physical computer and virtual machines each have 4 GB of RAM.

Each of these virtual machines would have their own operating system and function similarly to a typical computer.

---

## Benefits of Virtual Machines

Security professionals commonly use virtualization and virtual machines. Virtualization can increase security and efficiency.

### Security

One benefit is that virtualization can provide an isolated environment, or sandbox, on the physical host machine.

When a computer has multiple virtual machines, these virtual machines are “guests” of the computer. They are isolated from the host computer and other guest virtual machines.

This provides a layer of security because virtual machines can be kept separate from the other systems.

For example, if an individual virtual machine becomes infected with malware, it can be dealt with more securely because it is isolated from the other machines.

A security professional could also intentionally place malware on a virtual machine to examine it in a more secure environment.

**Note:** Although using virtual machines is useful when investigating potentially infected machines or running malware in a constrained environment, there are still risks. For example, a malicious program can escape virtualization and access the host machine. This is why you should never completely trust virtualized systems.

### Efficiency

Using virtual machines can also be an efficient and convenient way to perform security tasks.

You can open multiple virtual machines at once and switch easily between them. This allows you to streamline security tasks, such as testing and exploring various applications.

### City Bus Analogy

A single city bus has a lot of room and is an efficient way to transport many people simultaneously.

If city buses did not exist, then everyone on the bus would have to drive their own cars. This uses more gas, cars, and other resources than riding the city bus.

Similarly, many virtual machines can be hosted on the same physical machine. That way, separate physical machines are not needed to perform certain tasks.

---

## Managing Virtual Machines

Virtual machines can be managed with a software called a **hypervisor**.

Hypervisors help users manage multiple virtual machines and connect the virtual and physical hardware. Hypervisors also help with allocating the shared resources of the physical host machine to one or more virtual machines.

### Kernel-based Virtual Machine (KVM)

**Kernel-based Virtual Machine (KVM)** is an open-source hypervisor that is supported by most major Linux distributions. It is built into the Linux kernel, which means it can be used to create virtual machines on any machine running a Linux operating system without the need for additional software.

### Other Forms of Virtualization

In addition to virtual machines, there are other forms of virtualization. Some of these virtualization technologies do not use operating systems.

Examples:

- Multiple virtual servers can be created from a single physical server
- Virtual networks can be created to more efficiently use the hardware of a physical network

### Key Takeaways

- Virtual machines are virtual versions of physical computers and are one example of virtualization.
- Virtualization is a key technology in the security industry.
- It is important for security analysts to understand the basics of virtualization.
- There are many benefits to using virtual machines, such as isolation of malware and other security risks.
- However, there is still a risk of malicious software escaping virtualized environments.

---

## CLI vs. GUI

Previously, graphical user interfaces (GUI) and command-line interfaces (CLI) were explored. These are two important types of user interfaces.

### Graphical User Interface (GUI)

A graphical user interface (GUI) is a user interface that uses icons on the screen to manage different tasks on the computer.

### Command-Line Interface (CLI)

A command-line interface (CLI) is a text-based user interface that uses commands to interact with the computer.

### Display

One notable difference between these two interfaces is how they appear on the screen.

- A GUI has graphics and icons, such as icons on your desktop or taskbar for launching programs.
- A CLI only has text. It looks similar to lines of code.

### Function

These two interfaces also differ in how they function.

- A GUI only allows you to make one request at a time.
- A CLI allows you to make multiple requests at a time.

### Advantages of a CLI in Cybersecurity

The choice between using a GUI or CLI is partly based on personal preference, but security analysts should be able to use both interfaces.

Using a CLI can provide certain advantages.

#### Efficiency

Some prefer the CLI because it can be used more quickly when you know how to manage this interface.

For a new user, a GUI might be more efficient because it is easier for beginners to navigate.

Because a CLI can accept multiple requests at one time, it is more powerful when you need to perform multiple tasks efficiently.

For example, if you had to create multiple new files in your system, you could quickly perform this task in a CLI. If you were using a GUI, this could take much longer because you would have to repeat the same steps for each new file.

#### History File

For security analysts, using the Linux CLI is helpful because it records a history file of all the commands and actions in the CLI. If you were using a GUI, your actions are not necessarily saved in a history file.

For example, if you are responding to an incident using a playbook, the playbook’s instructions may require you to run a series of different commands. If you use a CLI, you can go back to the history and ensure all of the commands were correctly used. This can be helpful if there were issues using the playbook and you had to review the steps you performed in the command line.

Additionally, if you suspect an attacker has compromised your system, you might be able to trace their actions using the history file.

### Key Takeaways

- GUIs and CLIs are two types of user interfaces that security analysts should be familiar with.
- There are multiple differences between a GUI and a CLI, including their displays and how they function.
- When working in cybersecurity, a CLI is often preferred over a GUI because it can handle multiple tasks simultaneously and includes a history file.

---

## Terms and Definitions

| Term | Definition |
|---|---|
| Application | A program that performs a specific task |
| Basic Input/Output System (BIOS) | A microchip that contains loading instructions for the computer and is prevalent in older systems |
| Bootloader | A software program that boots the operating system |
| Command-line interface (CLI) | A text-based user interface that uses commands to interact with the computer |
| Graphical user interface (GUI) | A user interface that uses icons on the screen to manage different tasks on the computer |
| Hardware | The physical components of a computer |
| Legacy operating system | An operating system that is outdated but still being used |
| Operating system (OS) | The interface between computer hardware and the user |
| Random Access Memory (RAM) | A hardware component used for short-term memory |
| Unified Extensible Firmware Interface (UEFI) | A microchip that contains loading instructions for the computer and replaces BIOS on more modern systems |
| User interface | A program that allows the user to control the functions of the operating system |
| Virtual machine (VM) | A virtual version of a physical computer |
