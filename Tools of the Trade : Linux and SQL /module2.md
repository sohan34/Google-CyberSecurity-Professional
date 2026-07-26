# Course 4 — Module 2

## Linux Architecture

Understanding the Linux architecture is important for a security analyst. When you understand how a system is organized, it becomes easier to understand how it functions.

A request to complete a task starts with the user and then flows through:

- Applications
- The shell
- The Filesystem Hierarchy Standard
- The kernel
- The hardware

### User

The user is the person interacting with a computer. They initiate and manage computer tasks.

Linux is a multi-user system, which means that multiple users can use the same resources at the same time.

### Applications

An application is a program that performs a specific task.

There are many different applications on a computer. Some applications come pre-installed, such as calculators or calendars. Other applications may need to be installed, such as some web browsers or email clients.

In Linux, a package manager is often used to install applications.

**Package manager:** A tool that helps users install, manage, and remove packages or applications.

**Package:** A piece of software that can be combined with other packages to form an application.

### Shell

The shell is the command-line interpreter.

- Everything entered into the shell is text based.
- The shell allows users to give commands to the kernel and receive responses from it.
- You can think of the shell as a translator between you and your computer.
- The shell translates the commands you enter so that the computer can perform the tasks you want.

### Filesystem Hierarchy Standard (FHS)

The Filesystem Hierarchy Standard (FHS) is the component of the Linux OS that organizes data.

It specifies the location where data is stored in the operating system.

A **directory** is a file that organizes where other files are stored.

- Directories are sometimes called folders.
- They can contain files or other directories.

The FHS defines how directories, directory contents, and other storage is organized so the operating system knows where to find specific data.

### Kernel

The kernel is the component of the Linux OS that manages processes and memory.

- It communicates with applications to route commands.
- The Linux kernel is unique to the Linux OS.
- It is critical for allocating resources in the system.
- It controls all major functions of the hardware, which helps tasks get done more efficiently.

### Hardware

The hardware is the physical components of a computer.

Examples include:

- Hard drives
- CPUs

Hardware is categorized as either peripheral or internal.

#### Peripheral Devices

Peripheral devices are hardware components that are attached and controlled by the computer system.

- They are not core components needed to run the computer system.
- They can be added or removed freely.

Examples:

- Monitors
- Printers
- Keyboard
- Mouse

#### Internal Hardware

Internal hardware are the components required to run the computer.

Internal hardware includes a main circuit board and all components attached to it.

This main circuit board is also called the **motherboard**.

Internal hardware includes the following:

##### CPU

The Central Processing Unit (CPU) is a computer’s main processor, used to perform general computing tasks.

- The CPU executes instructions provided by programs.
- This enables programs to run.

##### RAM

Random Access Memory (RAM) is a hardware component used for short-term memory.

- Data is stored temporarily as you perform tasks.
- For example, if you are writing a report, the data needed is stored in RAM.
- After the program is closed, the data is deleted from RAM.
- Information in RAM cannot be accessed once the computer has been turned off.
- The CPU takes the data from RAM to run programs.

##### Hard Drive

The hard drive is a hardware component used for long-term memory.

- Programs and files are stored here for later access.
- Information on the hard drive can still be accessed after the computer is turned off and on again.
- A computer can have multiple hard drives.

### Key Takeaways

- It is important for security analysts to understand the Linux architecture and how these components are organized.
- The components of the Linux architecture are:
  - User
  - Applications
  - Shell
  - Filesystem Hierarchy Standard
  - Kernel
  - Hardware
- Each of these components is important in how Linux functions.

---

## Linux Distributions

Previously, Linux distributions were introduced, including **KALI LINUX™**. KALI LINUX™ is a trademark of OffSec.

In addition to KALI LINUX™, there are multiple other Linux distributions that security analysts should be familiar with.

### KALI LINUX™

KALI LINUX™ is an open-source distribution of Linux that is widely used in the security industry.

- It is Debian-based.
- It is pre-installed with many useful tools for penetration testing and digital forensics.

**Penetration test:** A simulated attack that helps identify vulnerabilities in systems, networks, websites, applications, and processes.

**Digital forensics:** The practice of collecting and analyzing data to determine what has happened after an attack.

These are key activities in the security industry.

### Ubuntu

Ubuntu is an open-source, user-friendly distribution that is widely used in security and other industries.

- It has both a command-line interface (CLI) and a graphical user interface (GUI).
- It is Debian-derived.
- It includes common applications by default.
- Users can download many more applications from a package manager, including security-focused tools.
- It has a large number of community resources to support users.
- It is widely used for cloud computing.
- As organizations migrate to cloud servers, cybersecurity work may more regularly involve Ubuntu derivatives.

### Parrot

Parrot is an open-source distribution that is commonly used for security.

- Like KALI LINUX™, it comes with pre-installed tools related to penetration testing and digital forensics.
- Like KALI LINUX™ and Ubuntu, it is based on Debian.
- It is considered user-friendly.
- It has a GUI that many find easy to navigate.
- It also has a CLI.

### Red Hat Enterprise Linux

Red Hat Enterprise Linux is a subscription-based distribution of Linux built for enterprise use.

- It is not free.
- This is a major difference from the previously mentioned distributions.
- Because it is built and supported for enterprise use, Red Hat offers a dedicated support team for customers to call about issues.

### AlmaLinux

AlmaLinux is a community-driven Linux distribution that was created as a stable replacement for CentOS.

- CentOS was an open-source distribution closely related to Red Hat.
- Its final stable release, CentOS 8, was in December 2021.
- CentOS used source code published by Red Hat to provide a similar platform.
- AlmaLinux is designed to be a drop-in replacement for CentOS 8.
- This ensures that applications and configurations that worked on CentOS will continue to function on AlmaLinux.

### Key Takeaways

- KALI LINUX™, Ubuntu, Parrot, Red Hat, and CentOS are all widely used Linux distributions.
- Security analysts should be aware of these distributions that they might encounter in their career.

---

## Package Managers

Previously, Linux distributions and package managers were introduced.

Linux applications are commonly distributed through package managers.

### Introduction to Package Managers

A **package** is a piece of software that can be combined with other packages to form an application.

- Some packages may be large enough to form applications on their own.
- Packages contain the files necessary for an application to be installed.
- These files include **dependencies**, which are supplemental files used to run an application.

**Package manager:** A tool that helps users install, manage, and remove packages or applications.

Linux uses multiple package managers.

**Note:** It is important to use the most recent version of a package when possible. The most recent version has the most up-to-date bug fixes and security patches. These help keep the system more secure.

### Types of Package Managers

Many commonly used Linux distributions are derived from the same parent distribution.

Examples:

- KALI LINUX™, Ubuntu, and Parrot come from Debian.
- CentOS comes from Red Hat.

This is useful when installing applications because certain package managers work with certain distributions.

- The Red Hat Package Manager (RPM) can be used for Linux distributions derived from Red Hat.
- Package managers such as dpkg can be used for Linux distributions derived from Debian.

Different package managers typically use different file extensions.

- RPM files use the `.rpm` extension.
- Debian-derived package managers such as dpkg use the `.deb` extension.

Examples:

- `Package-Version-Release_Architecture.rpm`
- `Package_Version-Release_Architecture.deb`

### Package Management Tools

In addition to package managers like RPM and dpkg, there are also package management tools that allow you to easily work with packages through the shell.

These tools are sometimes used instead of package managers because they make it easier to perform basic tasks, such as installing a new package.

Two notable tools are:

- Advanced Package Tool (APT)
- Yellowdog Updater Modified (YUM)

#### Advanced Package Tool (APT)

APT is a tool used with Debian-derived distributions.

- It is run from the command-line interface.
- It is used to manage, search, and install packages.

#### Yellowdog Updater Modified (YUM)

YUM is a tool used with Red Hat-derived distributions.

- It is run from the command-line interface.
- It is used to manage, search, and install packages.
- It works with `.rpm` files.

### Key Takeaways

- A package is a piece of software that can be combined with other packages to form an application.
- Packages can be managed using a package manager.
- There are multiple package managers and package management tools for different Linux distributions.
- Package management tools allow users to easily work with packages through the shell.
- Debian-derived Linux distributions use package managers like dpkg and tools like APT.
- Red Hat-derived distributions use the Red Hat Package Manager (RPM) or tools like YUM.

---

## Linux Shells

Knowing how to work with Linux shells is an important skill for cybersecurity professionals.

Shells can be used for many common tasks.

### Communicate Through a Shell

The shell is the command-line interpreter.

You can think of a shell as a translator between you and the computer system.

Shells allow you to:

- Give commands to the computer
- Receive responses from it

When you enter a command into a shell, the shell executes many internal processes to interpret your command, send it to the kernel, and return your results.

### Types of Shells

The many different types of Linux shells include:

- Bourne-Again Shell (bash)
- C Shell (csh)
- Korn Shell (ksh)
- Enhanced C shell (tcsh)
- Z Shell (zsh)

All Linux shells use common Linux commands, but they can differ in other features.

For example:

- ksh and bash use the dollar sign (`$`) to indicate where users type in their commands.
- Other shells, such as zsh, use the percent sign (`%`) for this purpose.

### Bash

Bash is the default shell in most Linux distributions.

- It is considered user-friendly.
- It can be used for basic Linux commands as well as larger projects.
- It is the most popular shell in the cybersecurity profession.
- You will use bash throughout this course as you learn and practice Linux commands.

### Key Takeaways

- Shells are a fundamental part of the Linux operating system.
- Shells allow you to give commands to the computer and receive responses from it.
- They can be thought of as a translator between you and your computer system.
- There are many different types of shells, but bash is the most commonly used shell in cybersecurity.
- You will learn how to enter Linux commands through the bash shell later in this course.
