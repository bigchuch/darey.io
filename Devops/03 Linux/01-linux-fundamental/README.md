# Introduction to Linux

In the dynamic landscape of technology, mastering the fundamentals is essential for anyone aspiring to excel in fields such as:

- DevOps  
- Cloud Computing  
- Software Development  
- Cybersecurity  
- Data Analysis/Science  
- Artificial Intelligence (AI)  
- Quality Assurance (QA) Testing  

This project is designed to equip you with a solid foundation in Linux. Understanding the technology from the basics lays the groundwork for success in various tech-centric careers.

---

## What Is Linux?

Linux is a free, open-source operating system similar to Windows or macOS, but it's more widely used for servers and supercomputers. It's known for its stability, security, and flexibility, allowing users to modify and distribute their versions.

Linux runs on a wide range of devices, from desktops to smartphones, and powers much of the internet's infrastructure. It's supported by a global community of developers who contribute to its many distributions, each tailored for specific needs or preferences.

---

## Linux Distributions

Linux distributions, often referred to as **distros**, are different flavors of the Linux operating system. They are all built using the Linux kernel but package it with a unique combination of software, libraries, and tools to provide a complete computing environment.

Key characteristics that can vary between distros include:

*   Desktop environments
*   Package managers
*   Software repositories
*   Default configurations
*   Branding

Choosing the right distribution depends on your specific needs, technical expertise, and the primary use case for the system (e.g., desktop, server, development).

Some of the popular Linux distributions include:

### Ubuntu:
Ubuntu is one of the most widely recognized Linux distributions, known for its user-friendliness and ease of installation. It's an excellent choice for those new to Linux, as well as for everyday desktop computing. Ubuntu boasts a large community, extensive documentation, and a vast repository of software packages, making it highly versatile.

*   **Use Cases:** Desktop use, development workstations, cloud deployments, and servers (especially for web applications and newer technologies).
*   **Key Strengths:** User-friendly, large community support, up-to-date software, good for beginners and developers.

![Ubuntu Logo](./img/ubuntu.png)

---

### CentOS (Community ENTerprise Operating System):
CentOS was historically favored in enterprise and server environments due to its stability, long-term support, and binary compatibility with Red Hat Enterprise Linux (RHEL), a commercial distribution. It was essentially a free, community-supported version of RHEL. System administrators often chose CentOS for its reliability and robustness for critical server workloads.

*   **Note:** CentOS Linux 8 reached its End-Of-Life (EOL) on December 31, 2021. CentOS Stream is now the upstream development platform for future RHEL releases. For users seeking a similar RHEL-compatible experience, alternatives like AlmaLinux and Rocky Linux have emerged.
*   **Use Cases (Historically):** Production servers, enterprise applications, web hosting, data centers requiring high stability and long support cycles.
*   **Key Strengths (Historically):** Stability, security, long-term support, RHEL compatibility.

![CentOS Logo](./img/centos.png)

---

### Debian:
Debian is renowned for its commitment to free and open-source software principles. It forms the basis for many other distributions, including Ubuntu. Debian provides a wide range of software packages and supports multiple hardware architectures. It is known for its stability and rigorous testing processes, making it a solid choice for servers and users who prioritize stability and adherence to FOSS ideals.

*   **Use Cases:** Servers (especially web, database, and mail servers), desktops for users prioritizing stability and free software, base for other distributions.
*   **Key Strengths:** Stability, vast software repositories, strong commitment to free software, wide hardware support.

![Debian Logo](./img/debian.png)

---

### Fedora:
Fedora is a cutting-edge distribution sponsored by Red Hat that focuses on integrating the latest software and technologies. It's a great choice for developers, enthusiasts, and those who want to experiment with new features and applications. Fedora often serves as a proving ground for technologies that may later be incorporated into Red Hat Enterprise Linux.

*   **Use Cases:** Developers, Linux enthusiasts, users wanting the latest software, testing new technologies.
*   **Key Strengths:** Up-to-date software, strong focus on innovation, active community, close ties to RHEL development.

![Fedora Logo](./img/fedora.png)

---


# Installation and Initial Setup


In this section, we will create a new server in the cloud, and gain access to it from out local enviroment. When we say "Local enviroment" we are referring to your laptop, or the desktop PC you are using to work or learn. which would have either windows, or Mac operating system in most cases. Then you will connect to the server in the cloud remotely straight from you laptop.

The setup will look like this.
![Setup](./img/setup%20look.png)

We will use AWS, a public cloud provider to creat the server in the cloud. For now, do not worry about trying to learn AWS becuase there is a complete course on that, and plenty of projects ahead that focuses on that.

Right now, all you need to know is that AWS can provide us with free virtual server called EC2 [Elastic Compute Cloud](https://aws.amazon.com/ec2/features/).

## Let us create an EC2 instance. ie a Linux Server
you can either watch the vidoes below to get yourself setup.
- [AWS account setup and Provision an ubuntu server](https://www.youtube.com/watch?v=xxKuB9kJoYM)
- [Connecting to you EC2 instance](https://www.youtube.com/watch?v=TxT6PNJts-s)

or follwing the guideline below.

**i. Register an AWS account following** [this instruction](https://repost.aws/knowledge-center/create-and-activate-aws-account)

- **ii. Sign into youo AWS account.**
- **iii. One the top left selct services and search for Elastic Cloud Compute (EC2).**
- **iv. From the menu on the left side, select instances.**
- **v. SSlect launch instance on the top right side.**
- **vi. Follow the image below to finish launching an instance.**
![AWS EC2](./img/launching%20instance%201.png)
![AWS EC2](./img/launching%20instance%202.png)
![AWS EC2](./img/lauching%20instance%203.png)

## Connecting to the Server

Now it's time to get onto the server you have just created in the cloud. You will need a number of things set up depending on your operating system.

1. **A client tool**: A client tool is a program on your computer that lets you communicate and give commands to a remote server. Imagine it as a doorway on your laptop that allows you to speak to a far-off computer as if it were right in front of you. By typing commands into a terminal, you can ask the remote server to perform tasks, retrieve data, or even run programs, all without being physically present near the server. This is especially useful for managing websites, running software, or accessing files from anywhere in the world, just by using simple text commands.

2. **A secure protocol**: A secure protocol is like a protected path over the internet that ensures the information you send from your computer to a remote server is safe from prying eyes. Imagine sending a secret letter through a series of locked, armored vehicles instead of a regular open road; that's what a secure protocol does for your data. It encrypts, or scrambles, your information so that only the intended recipient, the remote server, can understand it. The popular protocol for this purpose is called **SSH (Secure Shell)**.

---

## Client Tools to Install

If you are on Windows, you will need to have tools such as [MobaXterm](https://mobaxterm.mobatek.net/) installed. There are many other options such as:

- [PuTTY](https://www.putty.org/)
- [Git Bash](https://git-scm.com/downloads) – which is available by default when you install Git on Windows.
- PowerShell – This is available by default on every Windows computer. Even though you can use it to access Linux computers remotely, it is more optimized for Microsoft Windows.

> For simplicity, you should focus only on **MobaXterm**, which is perfect for all you need throughout this program.

---

## For macOS Users

Client terminal is already available, so you don't have to do anything. Simply open up the terminal by navigating to:

**Applications folder → Utilities folder → Terminal**
![Terminal](./img/terminal%20on%20mac.png)




          
# Connecting to Remote Server Using SSH

## Prerequisites
- A terminal application
- SSH key pair (`.pem` key file)
- Remote server (e.g., AWS EC2 instance) with public IP address

## Connection Steps

1. Open your terminal application

2. Locate your `.pem` key file
   - By default, it should be in your "Downloads" folder
   - Navigate to the Downloads folder using:
   ```bash
   cd ~/Downloads
   ```

   **Command Breakdown:**
   - `cd`: Change directory command
   - `~`: Shortcut for your home directory
   - `/Downloads`: The Downloads folder where your key file is likely stored

3. Verify your key file
   - Use the `ls -l` command to list files in the Downloads directory
   - Look for a file named something like `ubuntu.pem` (name may vary)

4. Connect to your server
   - First, locate your server's public IP address from the AWS EC2 Dashboard
   - Use the SSH command with your key file and IP address:
   ```bash
   ssh -i "your-key-file.pem" ubuntu@your-server-ip
   ```

## Important Notes
- Keep your `.pem` key file secure and never share it. Treat it like a password.
- The username (e.g., `ubuntu`, `ec2-user`, `centos`) may vary depending on your server's operating system (AMI - Amazon Machine Image).
- Make sure your server's security group settings (firewall rules in AWS) allow inbound SSH access on port 22 from your IP address or a trusted range.

## Troubleshooting

-   **Permission denied (publickey,gssapi-with-mic,password):**
    *   **Incorrect Key File:** Ensure you are using the correct `.pem` file specified with the `-i` option. Double-check the filename and path.
    *   **Incorrect Username:** The default username varies by AMI. For Ubuntu, it's often `ubuntu`. For Amazon Linux, it's `ec2-user`. For CentOS, it might be `centos` or `ec2-user`. Check the AMI documentation.
    *   **Key File Permissions (macOS/Linux):** Your `.pem` file must have strict permissions. Use `chmod 400 your-key-file.pem` to make it readable only by you. SSH will reject keys that are too open.
    *   **Server-side SSH Configuration:** While less common for new cloud instances, ensure the server's SSH daemon is configured to accept key-based authentication and that your public key is correctly installed if you set it up manually (not typical for initial EC2 connections with a `.pem` file).
-   **Connection timed out:**
    *   **Incorrect IP Address:** Verify you are using the correct public IP address or DNS name of your EC2 instance.
    *   **Server Not Running:** Ensure your EC2 instance is in a 'running' state in the AWS console.
    *   **Security Group/Firewall:** Check that your EC2 instance's security group allows inbound TCP traffic on port 22 (SSH) from your current IP address. Corporate or local firewalls might also block outbound SSH connections.
    *   **Network Issues:** There might be broader network connectivity problems either on your end or with the cloud provider.
-   **Host key verification failed:** This error occurs if the server's host key has changed since you last connected (e.g., if the server was rebuilt). To resolve this, you can remove the old key from your `~/.ssh/known_hosts` file. The error message usually tells you which line to remove.
-   **`ssh: connect to host <your-server-ip> port 22: Connection refused`**:
    *   **SSH Service Not Running on Server:** The SSH daemon (sshd) might not be running on the server or is not listening on port 22.
    *   **Firewall on Server:** A firewall on the server itself (like `ufw` or `firewalld`) might be blocking port 22, though security groups are the primary firewall for EC2.

![](./img/running%20instances%20in%20aws%20.png)




          
### 5. Connecting to the server using SSH. Simply run the command below.

```bash
ssh -i "ubuntu.pem" ubuntu@public_ip_address
```

Lets break down the command:

*   `ssh`: This is the command to initiate an SSH connection. SSH is a protocol used to securely access and manage a remote system over an unsecured network (The Internet is an unsecured network).
*   `-i "ubuntu.pem"`: The -i option specifies the path to a private key file used for authentication. In this case, `"ubuntu.pem"` is the private key file. This file is essential for proving your identity to the server without needing a password. The .pem file is often used when connecting to servers, for example, those hosted on AWS (Amazon Web Services).
*   `ubuntu@public_ip_address`: This part specifies the user and the server you're trying to connect to. `ubuntu` is the username on the remote server that you're logging in as, and `public_ip_address` should be replaced with the actual public IP address (or hostname) of the server you're trying to access. The `@` symbol separates the username from the server's address.

Once you establish a successful connection, you should see an output like the below which proves that you have successfully connected to your remote server.

![](./img/ssh%20into%20vm%20.png)

## Package Managers

Most of the time, when working on linux, there will be the need to install tools. Think about it, the servers are used to host websites, and there has to be a tool that will help in the rendering of the web ages. A commonly used tool is called "Nginx".

Since the servers are not your regular computers where you can go to a browser to click and download, there is the need to have package managers that can help achieve this.

Package managers in Linux are tools that automate the process of installing, updating, configuring, and removing software packages on a Linux server. They simplify the management of software by handling dependencies, versioning, and installation procedures. There are several package managers used in various Linux distributions.

**Commonly Used Package Managers**

*   **APT (Advanced Package Tool):** Used by Debian-based distributions such as Debian, Ubuntu, and derivatives. Commands include `apt-get` and `apt`. You will get to use this a lot very soon.
*   **YUM (Yellowdog Updater Modified):** Originally used by Red Hat and CentOS, `YUM` is now largely replaced by `dnf` in modern Red Hat-based distributions. It simplifies package management by resolving dependencies just like `apt`.
*   **DNF (Dandified YUM):** Used in modern versions of Red Hat-based distributions as a replacement for YUM. It provides improved performance and resolves some of the limitations of the older YUM tool.

## Installing, Updating and Removing Software

Since we are already on an Ubuntu-based server, let's explore how to install, update, and remove tools on a Linux server. These operations are fundamental to server management, allowing you to customize your server's capabilities and keep it secure.

1.  **Updating Package Lists (`sudo apt update`)**

    Before installing new software or updating existing packages, it's crucial to refresh your local package lists. Your server maintains a local cache of available packages from the repositories defined in its configuration (typically in `/etc/apt/sources.list` and `/etc/apt/sources.list.d/`).

    ```bash
    sudo apt update
    ```

    *   **`sudo`**: This command stands for "Super User Do". It allows you to execute commands with administrative (or root) privileges. Many system-level tasks, like installing software or updating the system, require these elevated permissions to modify system files and configurations.
    *   **`apt`**: This is the command-line interface for the Advanced Package Tool (APT), the package manager used by Debian and its derivatives like Ubuntu.
    *   **`update`**: This option tells `apt` to resynchronize the package index files from their sources. It doesn't install or upgrade any packages; it just downloads the latest information about available packages, their versions, and dependencies. This ensures that when you later try to install or upgrade software, `apt` knows where to get the newest versions and how to handle dependencies correctly.

    **Why is this critical?**
    Running `sudo apt update` regularly is vital for security and stability. It ensures that your system is aware of the latest security patches and software versions. Without updating the package lists, your system might install outdated software with known vulnerabilities or fail to resolve dependencies correctly.

    For **Red Hat-based systems** (like older CentOS, Fedora):
    ```bash
    sudo yum update
    ```
    (Note: `yum update` on its own often updates package lists *and* performs upgrades. To only update lists, `yum check-update` can be used, though `yum update` is more common practice before installing.)
    For newer Fedora/RHEL versions:
    ```bash
    sudo dnf check-update
    ```

2.  **Installing Software Packages (e.g., `tree`)**

    Let's install a simple utility called `tree`, which displays directory structures in a tree-like format.

    For **Debian/Ubuntu**:
    ```bash
    sudo apt install tree
    ```
    *   **`install`**: This `apt` option is used to install new packages.
    *   **`tree`**: This is the name of the package you want to install.
    `apt` will automatically handle downloading the package and any dependencies it requires.

    For **Red Hat/Fedora**:
    ```bash
    sudo yum install tree
    ```
    or for newer Fedora/RHEL versions:
    ```bash
    sudo dnf install tree
    ```

    You will often be prompted to confirm the installation (e.g., `Do you want to continue? [Y/n]`). Type `Y` and press Enter.

    ![](./img/sudo%20apt%20install%20tree.png)

3.  **Verifying Installed Packages**

    After installation, you can verify that `tree` is installed by trying to run it or checking its version:
    ```bash
    tree --version
    ```
    Or simply:
    ```bash
    tree
    ```
    (This will show the tree structure of your current directory).

4.  **Updating Installed Packages (`sudo apt upgrade`)**

    After updating your package lists with `sudo apt update`, you can upgrade all currently installed packages to their newest versions available in the repositories.

    For **Debian/Ubuntu**:
    ```bash
    sudo apt upgrade
    ```
    *   **`upgrade`**: This `apt` option upgrades all currently installed software packages to the newest versions, based on the information gathered by `sudo apt update`. It will not remove any packages; if an upgrade requires removing another package, it will be skipped.

    **Why is `sudo apt upgrade` critical?**
    Regularly upgrading packages is essential for:
    *   **Security:** Upgrades often include patches for security vulnerabilities discovered in older software versions. Keeping your software up-to-date is a primary defense against cyber threats.
    *   **Stability and Bug Fixes:** Newer versions often include bug fixes that improve the stability and reliability of your software and the overall system.
    *   **New Features:** Upgrades can also introduce new features and performance improvements.

    It's good practice to run `sudo apt update` followed by `sudo apt upgrade` regularly (e.g., weekly or monthly, depending on the server's role) to keep your system secure and performing optimally.

    For **Red Hat/Fedora**:
    ```bash
    sudo yum upgrade
    ```
    or for newer Fedora/RHEL versions:
    ```bash
    sudo dnf upgrade
    ```

5.  **Removing Software Packages (e.g., `tree`)**

    If you no longer need a package, you can remove it.

    For **Debian/Ubuntu**:
    ```bash
    sudo apt remove tree
    ```
    *   **`remove`**: This `apt` option uninstalls packages. It removes the package files but may leave behind configuration files.

    To remove a package and its configuration files, you can use `purge`:
    ```bash
    sudo apt purge tree
    ```

    To remove unused packages that were automatically installed as dependencies and are no longer needed:
    ```bash
    sudo apt autoremove
    ```

    For **Red Hat/Fedora**:
    ```bash
    sudo yum remove tree
    ```
    or for newer Fedora/RHEL versions:
    ```bash
    sudo dnf remove tree
    ```

    ![](./img/suto%20apt%20remove%20tree.png)

## Practice Exercise

**Practice:** Explore other tools you can install on a Linux server and practice everything again. For example, install the tool `nginx`

In the next step, we would be engaging in more hands on project that involve using commands on a Linux system. Working with Linux commands typically includes tasks such as navigating the file system, managing files and directories and manipulating permissions.

        

        
        
        

        