# Course 4 — Module 3

## Filesystem Hierarchy Standard (FHS)

The Filesystem Hierarchy Standard (FHS) is the component of Linux that organizes data. It defines how directories, directory contents, and other storage are organized in the operating system.

A file’s location can be described by a **file path**. In a file path, the different levels of the hierarchy are separated by a forward slash (`/`).

### Root Directory

The root directory is the highest-level directory in Linux, and it is always represented with a forward slash (`/`). All subdirectories branch off the root directory. Subdirectories can continue branching out to as many levels as necessary.

### Standard FHS Directories

Directly below the root directory are standard FHS directories. Examples include:

- `/home`
- `/bin`
- `/etc`
- `/tmp`
- `/mnt`

#### /home

Each user in the system gets their own home directory.

#### /bin

This directory stands for “binary” and contains binary files and other executables.

**Executables** are files that contain a series of commands a computer needs to follow to run programs and perform other functions.

#### /etc

This directory stores the system’s configuration files.

#### /tmp

This directory stores many temporary files. The `/tmp` directory is commonly used by attackers because anyone in the system can modify data in these files.

#### /mnt

This directory stands for “mount” and stores media, such as USB drives and hard drives.

**Pro Tip:** You can use the `man hier` command to learn more about the FHS and its standard directories.

### User-Specific Subdirectories

Under `/home` are subdirectories for specific users.

For example, users may have personal subdirectories such as:

- projects
- logs
- reports

If the path leads to a subdirectory below the user’s home directory, the home directory can be represented as the tilde (`~`).

Example:

- `/home/analyst/logs`
- `~/logs`

You can navigate to specific subdirectories using **absolute** or **relative** file paths.

- **Absolute file path:** The full file path starting from the root.
- **Relative file path:** The file path starting from the current directory.

Relative file paths can use:

- `.` to represent the current directory
- `..` to represent the parent directory

Example:

- `../projects`

---

## Key Commands for Navigating the File System

The following Linux commands can be used to navigate the file system:

- `pwd`
- `ls`
- `cd`

### `pwd`

The `pwd` command prints the working directory to the screen. It returns the directory you are currently in.

The output gives you the absolute path to this directory.

Example:

- If you are in your home directory and your username is `analyst`, entering `pwd` returns `/home/analyst`.

**Pro Tip:** To learn what your username is, use the `whoami` command.

- `whoami` returns the username of the current user.

Example:

- If your username is `analyst`, entering `whoami` returns `analyst`.

### `ls`

The `ls` command displays the names of the files and directories in the current working directory.

Example:

- `ls` may return directories such as `logs` and a file called `updates.txt`.

If you want to return the contents of a directory that is not your current working directory, you can add an argument after `ls` with the absolute or relative file path.

Examples:

- `ls /home/analyst/projects`
- `ls projects`

### `cd`

The `cd` command navigates between directories.

To navigate to a subdirectory of the current directory, add the subdirectory name after `cd`.

Example:

- If you are in `/home/analyst` and want to navigate to `projects`, enter `cd projects`.

You can also navigate to any specific directory by entering the absolute file path.

Example:

- If you are in `/home/analyst/projects`, entering `cd /home/analyst/logs` changes your current directory to `/home/analyst/logs`.

**Pro Tip:** You can use the relative file path and enter `cd ..` to go up one level in the file structure.

Example:

- If the current directory is `/home/analyst/projects`, entering `cd ..` changes your working directory to `/home/analyst`.

---

## Common Commands for Reading File Content

The following Linux commands are useful for reading file content:

- `cat`
- `head`
- `tail`
- `less`

### `cat`

The `cat` command displays the content of a file.

Example:

- `cat updates.txt` returns everything in the `updates.txt` file.

### `head`

The `head` command displays just the beginning of a file, by default 10 lines.

It is useful when you want to know the basic contents of a file but do not need the full contents.

Example:

- `head updates.txt` returns only the first 10 lines of the `updates.txt` file.

**Pro Tip:** To change the number of lines returned by `head`, use `-n`.

Example:

- `head -n 5 updates.txt`

### `tail`

The `tail` command does the opposite of `head`.

It displays just the end of a file, by default 10 lines.

Example:

- `tail updates.txt` returns only the last 10 lines of the `updates.txt` file.

**Pro Tip:** `tail` can be used to read the most recent information in a log file.

### `less`

The `less` command returns the content of a file one page at a time.

Example:

- `less updates.txt` changes the terminal window to display the contents of `updates.txt` one page at a time.

This allows you to move forward and backward through the content.

Keyboard controls in `less`:

- `Space bar`: Move forward one page
- `b`: Move back one page
- `Down arrow`: Move forward one line
- `Up arrow`: Move back one line
- `q`: Quit and return to the previous terminal window

---

## Key Takeaways

It is important for security analysts to be able to navigate Linux and the file system of the FHS.

Some key commands for navigating the file system include:

- `pwd`
- `ls`
- `cd`

Reading file content is also an important skill in the security profession.

This can be done with commands such as:

- `cat`
- `head`
- `tail`
- `less`

---

## Filtering for Information

Filtering is selecting data that match a certain condition.

Example:

- If a virus in your system only affected `.txt` files, you could use filtering to find these files quickly.

Filtering allows you to search based on specific criteria, such as:

- File extension
- A string of text

### `grep`

The `grep` command searches a specified file and returns all lines in the file containing a specified string or text.

`grep` commonly takes two arguments:

- A specific string to search for
- A specific file to search through

Examples:

- `grep OS updates.txt`
- `grep error time_logs.txt`

In the second example:

- `error` is the term you are looking for
- `time_logs.txt` is the file being searched

### Piping

The pipe command is accessed using the pipe character (`|`).

Piping sends the standard output of one command as standard input to another command for further processing.

- **Standard output:** Information returned by the OS through the shell
- **Standard input:** Information received by the OS via the command line

The pipe character (`|`) is located in various places on a keyboard. On many keyboards, it is on the same key as the backslash character (`\`).

When used with `grep`, the pipe can help you find directories and files containing a specific word in their names.

Example:

- `ls /home/analyst/reports | grep users`

In this example:

- `ls` lists the names of the files and directories in `reports`
- The output is sent to the command after the pipe
- `grep users` returns all file or directory names containing `users`

Piping is a general form of redirection in Linux and can be used for multiple tasks other than filtering.

### `find`

The `find` command searches for directories and files that meet specified criteria.

Examples of criteria include files and directories that:

- Contain a specific string in the name
- Are a certain file size
- Were last modified within a certain time frame

When using `find`, the first argument after `find` indicates where to start searching.

Example:

- `find /home/analyst/projects`

After this first argument, you need to indicate your search criteria.

Options modify the behavior of a command and commonly begin with a hyphen (`-`).

#### `-name` and `-iname`

One key criterion analysts might use with `find` is finding file or directory names that contain a specific string.

The string must be entered in quotes after `-name` or `-iname`.

- `-name` is case-sensitive
- `-iname` is not case-sensitive

Examples:

- `find /home/analyst/projects -name "*log*"`
- `find /home/analyst/projects -iname "*log*"`

The `*log*` portion is the search criteria and means to search for the string `log` surrounded by zero or more characters.

An asterisk (`*`) is a wildcard used to represent zero or more unknown characters.

If you use `-name`, files with names such as `Log` or `LOG` will not be returned because it is case-sensitive. These would be returned when using `-iname`.

#### `-mtime`

Security analysts might also use `find` to locate files or directories last modified within a certain time frame.

Example:

- `find /home/analyst/projects -mtime -3`

This returns all files and directories in the `projects` directory that have been modified within the past three days.

The `-mtime` option is based on days:

- `-mtime +1` = modified more than one day ago
- `-mtime -1` = modified less than one day ago

**Note:** `-mmin` can be used instead of `-mtime` if you want to base the search on minutes rather than days.

---

## Key Takeaways

Filtering for information using Linux commands is an important skill for security analysts so they can customize data to fit their needs.

Three key Linux commands for this are:

- `grep`
- piping (`|`)
- `find`

These commands can be used to navigate and filter for information in the file system.

---

## Creating and Modifying Directories

### `mkdir`

The `mkdir` command creates a new directory.

You can provide the new directory as either:

- An absolute file path, which starts from the root
- A relative file path, which starts from your current directory

Example:

- To create a new directory called `network` in `/home/analyst/logs`, enter:
  - `mkdir /home/analyst/logs/network`

If you are already in `/home/analyst/logs`, you can also enter:

- `mkdir network`

**Pro Tip:** You can use `ls` to confirm the new directory was added.

### `rmdir`

The `rmdir` command removes, or deletes, a directory.

Example:

- `rmdir /home/analyst/logs/network`

**Note:** `rmdir` cannot delete directories with files or subdirectories inside.

Example:

- `rmdir /home/analyst` returns an error message.

---

## Creating and Modifying Files

### `touch` and `rm`

The `touch` command creates a new file.

This file will not have any content inside.

Example:

- If your current directory is `/home/analyst/reports`, entering `touch permissions.txt` creates a new file called `permissions.txt` in the `reports` subdirectory.

The `rm` command removes, or deletes, a file.

This command should be used carefully because it is not easy to recover files deleted with `rm`.

Example:

- `rm permissions.txt`

**Pro Tip:** You can verify that `permissions.txt` was successfully created or removed by entering `ls`.

### `mv` and `cp`

You can also use `mv` and `cp` when working with files.

- `mv` moves a file or directory to a new location.
- `cp` copies a file or directory into a new location.

The first argument after `mv` or `cp` is the file or directory you want to move or copy, and the second argument is the location you want to move or copy it to.

Examples:

- `mv permissions.txt /home/analyst/logs`
- `cp permissions.txt /home/analyst/logs`

Moving a file removes it from its original location. Copying a file does not remove it from its original location.

The `mv` command can also be used to rename files.

Example:

- `mv permissions.txt perm.txt`

This renames `permissions.txt` to `perm.txt`.

---

## Nano Text Editor

`nano` is a command-line file editor that is available by default in many Linux distributions.

- Many beginners find it easy to use.
- It is widely used in the security profession.
- You can perform multiple basic tasks in `nano`, such as creating new files and modifying file contents.

To open an existing file in `nano` from the directory that contains it, enter `nano` followed by the file name.

Example:

- `nano permissions.txt`

You can also provide the absolute file path if you are not in the directory that contains the file.

To create a new file in `nano`, enter `nano` followed by a new file name.

Example:

- `nano authorized_users.txt`

Saving and exiting:

- `Ctrl + O` = Save a file
- `Ctrl + X` = Exit `nano`

**Note:** Vim and Emacs are also popular command-line text editors.

---

## Standard Output Redirection

There is an additional way to write to files.

Previously, you learned about standard input and standard output.

- **Standard input:** Information received by the OS via the command line
- **Standard output:** Information returned by the OS through the shell

You also learned about piping (`|`).

In addition to the pipe, you can use the right angle bracket (`>`) and double right angle bracket (`>>`) operators to redirect standard output.

When used with `echo`, the `>` and `>>` operators can send the output of `echo` to a specified file rather than the screen.

- `>` overwrites the existing file
- `>>` adds content to the end of the existing file

The `>` operator should be used carefully because it is not easy to recover overwritten files.

Examples:

- `echo "last updated date" >> permissions.txt`
- `echo "time" > permissions.txt`

If the file does not already exist, both `>` and `>>` will create a new file with the specified name.

---

## Key Takeaways

Knowing how to manage the file system in Linux is an important skill for security analysts.

Useful commands include:

- `mkdir`
- `rmdir`
- `touch`
- `rm`
- `mv`
- `cp`

When writing to files, security analysts can use:

- The `nano` text editor
- The `>` operator
- The `>>` operator

---

## Responsible Use of Sudo

To manage authorization and authentication, you need to be a root user or a user with elevated privileges to modify the system.

The root user can also be called the **super user**.

You can become a root user by logging in as the root user. However, running commands as the root user is not recommended in Linux because it can create security risks if malicious actors compromise that account.

It is also easy to make irreversible mistakes, and the system cannot track who ran a command.

For these reasons, rather than logging in as the root user, it is recommended to use `sudo` in Linux when you need elevated privileges.

The `sudo` command temporarily grants elevated permissions to specific users.

The name of this command comes from **super user do**.

Users must be given access in a configuration file called the **sudoers file**.

Although using `sudo` is preferable to logging in as the root user, users with elevated permissions to use `sudo` might be more at risk in the event of an attack.

You can compare this to a hotel with a master key:

- The master key can be used to access any room in the hotel.
- Some workers need this key to perform their work.
- If someone gained access to the worker’s ID badge and master key, they could access any room.

In this example:

- The worker with the master key represents a user using `sudo` for elevated privileges.

Because of the dangers of `sudo`, only users who really need to use it should have these permissions.

Even if you need access to `sudo`, be careful about using it with only the commands you need and nothing more.

Running commands with `sudo` allows users to bypass the typical security controls that are in place to prevent elevated access by an attacker.

**Note:** Be aware of `sudo` if copying commands from an online source. Do not use `sudo` accidentally.

---

## Authentication and Authorization with Sudo

You can use `sudo` with many authentication and authorization management tasks.

- **Authentication:** The process of verifying who someone is.
- **Authorization:** The concept of granting access to specific resources in a system.

### `useradd`

The `useradd` command adds a user to the system.

Example:

- `sudo useradd fgarcia`

Options:

- `-g`: Sets the user’s default group, also called the primary group
- `-G`: Adds the user to additional groups, also called supplemental or secondary groups

Examples:

- `sudo useradd -g security fgarcia`
- `sudo useradd -G finance,admin fgarcia`

### `usermod`

The `usermod` command modifies existing user accounts.

The same `-g` and `-G` options from `useradd` can be used with `usermod` if a user already exists.

#### Changing the Primary Group

To change the primary group of an existing user, use `-g`.

Example:

- `sudo usermod -g executive fgarcia`

#### Adding a Supplemental Group

To add a supplemental group for an existing user, use `-G` and `-a`.

- `-a` appends the user to an existing group and is only used with `-G`

Example:

- `sudo usermod -a -G marketing fgarcia`

**Note:** If you do not include `-a`, `-G` will replace any existing supplemental groups with the groups specified after `usermod`.

Other options for `usermod`:

- `-d`: Changes the user’s home directory
- `-l`: Changes the user’s login name
- `-L`: Locks the account so the user cannot log in

Example:

- `sudo usermod -d /home/garcia_f fgarcia`

### `userdel`

The `userdel` command deletes a user from the system.

Example:

- `sudo userdel fgarcia`

Be careful before deleting a user using this command.

`userdel` does not delete the files in the user’s home directory unless you use the `-r` option.

Example:

- `sudo userdel -r fgarcia`

Before deleting any user files, you should ensure you have backups in case you need them later.

**Note:** Instead of deleting the user, you could consider deactivating their account with `usermod -L`. This prevents the user from logging in while still giving you access to their account and associated permissions.

### `chown`

The `chown` command changes ownership of a file or directory.

You can use `chown` to change user or group ownership.

Examples:

- `sudo chown fgarcia access.txt`
- `sudo chown :security access.txt`

You must enter a colon (`:`) before the group name to designate it as a group.

### Key Takeaways

- Authentication is the process of a user verifying their identity.
- Authorization is the process of determining what they have access to.
- You can use `sudo` to temporarily run commands with elevated privileges to complete authentication and authorization management tasks.
- `useradd`, `userdel`, `usermod`, and `chown` can be used to manage users and file ownership.

---

## Linux Community and Support Resources

Linux has a large online community, which is a huge resource for users of all levels.

You can often find answers to questions with a simple online search.

Troubleshooting issues by searching and reading online is an effective way to discover how others approached your issue. It is also a good way for beginners to learn more about Linux.

The **UNIX and Linux Stack Exchange** is a trusted resource for troubleshooting Linux issues.

- It is a question-and-answer website where community members can ask and answer questions about Linux.
- Community members vote on answers, so higher-quality answers are displayed at the top.
- Many of the questions are related to specific topics from advanced users.

---

## Integrated Linux Support

Linux also has several commands that you can use for support.

### `man`

The `man` command displays information on other commands and how they work.

It is short for **manual**.

Example:

- `man chown`

The output of `man` is also called a **man page**.

### `apropos`

The `apropos` command searches the man page descriptions for a specified string.

Man pages can be lengthy and difficult to search through if you are looking for a specific keyword.

To use `apropos`, enter the keyword after `apropos`.

Example:

- `apropos graph`

You can also include the `-a` option to search for multiple words.

Example:

- `apropos -a graph editor`

This outputs man pages that contain both the words `graph` and `editor` in their descriptions.

### `whatis`

The `whatis` command displays a description of a command on a single line.

Example:

- `whatis nano`

This command is useful when you do not need a detailed description, just a general idea of the command.

It can be used as a reminder or after discovering a new command through a colleague or online resource.

### Key Takeaways

- There are many resources available for troubleshooting issues or getting support for Linux.
- Linux has a large global community of users who ask and answer questions on online resources such as the Unix and Linux Stack Exchange.
- You can also use integrated support commands in Linux, such as:
  - `man`
  - `apropos`
  - `whatis`

---

## Resources for More Information

There are many resources available online that can help you learn new Linux concepts, review topics, or ask and answer questions with the global Linux community.

The Unix and Linux Stack Exchange is one example, and you can search online to find others.
