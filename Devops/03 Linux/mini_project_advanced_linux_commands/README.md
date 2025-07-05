# Advanced Linux Commands

## File Permissions and Access Rights

Understanding how to manage file permissions and ownership is crucial in Linux. This knowledge empowers you to control access to files and directories, ensuring the security and integrity of your system. Let's explore some essential commands and concepts related to file permissions and ownership.

In Linux, managing file permissions and ownership is vital for controlling who can access, modify, or execute files and directories. Understanding these concepts allows you to maintain the security and integrity of your system. Let's delve into the key commands and concepts related to file permissions and ownership.

---

## Numeric Representation of Permissions

In Linux, permissions are represented using numeric values. Each permission (**no permission**, **read**, **write**, and **execute**) is assigned a numeric value:

- **no permissions** = `0`
- **read** = `4`
- **write** = `2`
- **execute** = `1`

These values are combined to represent the permissions for each user class. Let's consider a few examples:

---

### Permissions Represented by 7

- `4` (read) + `2` (write) + `1` (execute) = **7**
- **Symbolic**: `rwx`
- **Meaning**: Read, write, and execute permissions are all granted.
- **Example Context**: A script file that the owner needs to read, modify, and execute.

---

### Permissions Represented by 5

- `4` (read) + `1` (execute) = **5**
- **Symbolic**: `r-x`
- **Meaning**: Read and execute permissions are granted, but write permission is not.
- **Example Context**: A shared library or a command tool that users can execute and read but not modify.

---

### Permissions Represented by 6

- `4` (read) + `2` (write) = **6**
- **Symbolic**: `rw-`
- **Meaning**: Read and write permissions are granted, but execute permission is not.
- **Example Context**: A document or a configuration file that the owner needs to read and modify but not execute.

---

## Shorthand Representation of Permissions

In addition to the numeric way of showing permissions, Linux also has a shorthand, or symbolic, method for representing file permissions.

---

## Understanding User Classes from a Permissions Perspective

Before diving into shorthand permissions, it's important to understand the concept of **user classes** in the context of Linux permissions. Think of user classes as categories of users that Linux recognizes when deciding who can do what with a file. There are three main classes:

- **Owner**: The person who created the file. Often referred to as `user`.
- **Group**: A collection of users who share certain permissions for the file.
- **Others**: All other users on the system.

## The Role of Hyphens (-) in Permission Representation

When dicussing permission, you might notice hyphens (-) being mentioned. In the contect of linux file permissions, a hyphen doesnt acutally reprensnet a user class. Instead, its used in symbolic representation of permissions of show the absence of permissions.

Lets get a bit practical with exmaples. Get ontop your linux terminal and run **ls -latr** 

![ls -latr](./img/ls%20-latr.png)

Let’s break it down to understand what each part means:

* In the output above, you will notice that some of the first character can be a - or d: d means it’s a directory, - means it’s a file.

* The next three characters (rwx) show the permissions for the owner. r stands for read, w for write, and x for execute.

* If a permission is not granted, you’ll see - in its place (e.g., r-x means read and execute permissions are granted, but write permission is not).

* The hyphen separates owner, group, and others.

* The following three characters after the owner’s permissions represent the group’s permissions, using the same r, w, and x notation.

* The last three characters show the permissions for others.


The order the user class is represented is as follow:
* The first hyphen "-" is the user
* The second hyphen "-" is the group
* The third hyphen "-" is others

## File Permission Commands

To manage file permissions and ownership, Linux provides several commands:

## chmod command

The `chmod` command allows you to modify file permissions. You can use both symbolic and numeric representations to assign permissions to the user, group, and others.

Lets see an example.

Create an empty file using the `touch` command

```bash
touch script.sh
```
Check the permission of the file using the `ls -latr` command

![ls -latr](./img/file%20permision.png)

Absolutely! Here’s the final Markdown content — clean and ready for you to copy directly:

## What do you think the permission of the above output represent?

Now lets update the permission so that all the user classes will have execute permission:

```bash
chmod +x script.sh
```
The above command uses the chmod command with the +x option to grant execute permission to the file script.sh. The +x option adds the execute permission to the existing permissions for all the user classes.

Now lets check what the file permissions look like:

![ls -latr](./img/update%20with%20execute%20permission.png)

The same command can be executed to achieve the same result using the numbers approach:

```bash
chmod 755 script.sh
```

To add execute permissions for all (user, group, others), you would add 1 to each of the three categories, resulting in 755:
* (4 + 2 + 1) = 7 for the user (read, write, and execute),
* (4 + 1) = 5 for the group (read and execute),
* (4 + 1) = 5 for others (read and execute).

Let’s consider another example. Imagine the owner of a file is currently the only one with full permissions to **note.txt**

To allow group members and others to read, write, and execute the file, change it to the -rwxrwxrwx permission type, whose numeric value is 777:

```bash
chmod 777 note.txt
```

check the output

![](./img/full%20permission.png)

Here’s the Markdown-formatted README.md content based solely on the image you provided:

Now, notice the dash `("-")` in the first position represents the file type and not a user class. It indicates that the entry is a regular file.

## chown command

The `chown` command allows you to change the ownership of files, directories, or symbolic links to a specified username or group.

### Basic format:
```bash
chown [option] owner[:group] file(s)
```

For example, let’s assume there is a user on the server called “john”, a group on the server called “developers”, and you want the owner of filename.txt changed from “dare” to “john”, and to also ensure that any user in the developer group has ownership of the file as well:

The command would look like below:
```bash
chown john:developer filename.txt
```
Check the output with ls -latr command on this file to then see the new changes.

⸻

## Superuser Privileges

It is often necessary to become the superuser to perform important tasks in Linux, but as we know, we should not stay logged in as the superuser. In most Linux distributions, there is a command that can give you temporary access to the superuser’s privileges. This program is called sudo (short for super user) and can be used in those cases when you need to be the superuser for a small number of tasks.

To use the superuser privileges, simply type sudo before the command you will be invoking.

To switch to the root user, simply run:

```bash
sudo -i
```
![](./img/switching%20to%20root%20user.png)

You can type **exit** to leave the shell.

Here is the README.md content based on the image you provided, properly formatted in Markdown:

# User Management on Linux

As a DevOps engineer, you are also going to be doing systems administration which involves managing different users on the servers. You should know how to create a new user, or group, modify their permissions, update password and such similar tasks.

---

## Creating a User

To create a new user on Ubuntu Server, you can use the `adduser` command. Assuming the name of the user to be created is **joe**, open the terminal and run the following command:

```bash
sudo adduser johndoe
```
Running this command will prompt you to enter and confirm a password for the new user. You will also be asked to provide some additional information about the user, such as their full name and contact information. Once you provide the necessary details, the user account will be created, and a home directory will be automatically generated for the user.

The home directory represents a file system directory created in the name of the user. Such as /home/johndoe. This is where each user created on the server will store their respective data.

⸻

Example Terminal Output:

![](./img/adding%20a%20user.png)

Here is the README.md content formatted from the image you provided:

# Granting Administrative Privileges

By default, newly created user accounts do not have administrative privileges. To grant administrative access to a user, you can add the user to the sudo group. Users in the sudo group can run commands with administrative privileges. To add the `johndoe` user to the sudo group, run:

```bash
sudo usermod -aG sudo johndoe
```
Explanation:
* usermod: This is a command that modifies user account properties.
* -aG: These are flags used with the usermod command.
* -a stands for “append” and is used to add the user to the specified group(s) without removing them from other groups they may already belong to.
* -G stands for “supplementary groups” and is followed by a comma-separated list of groups. It specifies the groups to which the user should be added or modified.
* In the given command, -aG sudo is used to add the user johndoe to the sudo group.
* The sudo group is typically associated with administrative or superuser privileges. By adding johndoe to the sudo group, the user gains the ability to execute commands with elevated privileges.

⸻

🛠 Tasks for you:
* Log out and log back in as the newly created user.
* Navigate to the /home/johndoe directory to explore what has been created.
🔧 Tip: Use the cd command.

⸻

### Switching User Accounts

To start using the system as another user, you will need to use the su command to switch.

To switch to another user account, use the su command followed by the username. For example, to switch to the johndoe account, run:

```bash
su johndoe
```
You will be prompted to enter the password for the user. Once authenticated, you will switch to the user's environment

Here is the README.md content based on the latest image you uploaded:

# Modifying User Accounts

## Changing User Password

To change the password for a user, use the `passwd` command followed by the username. For example, to change the password for `johndoe`, run:

```bash
sudo passwd johndoe
```
You will be prompted to enter and confirm the new password for the user.

🛠 Tasks for you:
	•	Test the updated password by logging on to the server using the newly updated password.

⸻

Creating a Group

To create a new group, use the groupadd command. For example, to create a group named “developers”, use:

```bash
sudo groupadd developers
```

⸻

### Adding Users to the Group

Use the usermod command to add users to the group. For instance, to add users “john” and “jane” to the “developers” group:

``` bash
sudo usermod -aG developers johndoe
```

	The -aG options append the “developers” group to the users’ existing group memberships.

⸻

### Verifying Group Memberships

To confirm the group memberships for a specific user, use the id command. For example, to check the group memberships for the user johndoe:

```bash
id johndoe
```
This command displays information abouut the user **Johndoe**, including the groups they belong to, shuch as **developers**

![](./img/id%20johndoe.png)

## 🧹 Deleting a User

To delete a user, run the command below:

```bash
sudo userdel username
```
### Ensuring Proper Group Permissions

Groups in Linux are often used to manage permissions for files and directories. Ensure that the relevant files or directories have the appropriate group ownership and permissions.

➤ Grant Group Ownership

To grant the "developers" group ownership of a directory:

```bash
sudo chown :developers /path/to/directory
```
To grant read and write permissions to the group:

```bash
sudo chmod g+rw /path/to/directory
```
## side hustle task 3
 - Create a group on the server and name it **devops**
 - Create 5  user ['**Mary**', '**Mohammed**', '**Ravi**', '**Tunji**', '**Sofia**'], and ensure each belongs to the devops group
- create a folder for each user in the **/home** directory
- Ensure that the group ownership of each created folder belongs to the **devops** group
![img](./img/side%20task%203.png)
