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

Linux distributions, often referred to as **distros**, are different flavors of the Linux operating system built using the Linux kernel. These distros package the Linux kernel with a range of software, libraries, and tools to provide a functional computing environment.They offer different configurations, desktop environments, package managers, software repositories,and them they are branded. Some of the linux distributions are:

### Ubuntu:
Ubuntu is one of the most widely recognised Linux distribtuions, known for its user-friendliness and ease of installation. Its an excellent choice for those new to linx, as well as for everyday deesktop computing. Ubuntu has server editions for web hosting and cloud development.
![Ubuntu](./img/ubuntu.png)

---

### CentOS:
CentOS is favoured in enterprice and server environment due to its stabilily and long-term support. it is essentially a free and open-source version of Red Hat Enterprise Linux (RHEL) which is another distro itself. but requted paid licence. System administrators often choose CentOS because its free, reliable and rebust.
![CentOS](./img/centos.png)

---

### Debian:
Debain is also know for its commitment to free and open source software principle. Makes Linux available for free, provides a wide range of software packages and supports multiple hardware architectures.
![Debian](./img/debian.png)

---

### Fedora
Fedora is a cutting-edge distribution that focuses on intergrating the lastet software and technoligies. It's a greate choise for those who want to experiment with features and applications.Fedora also server as a test groun for Red Hat's Enterprise Linux products.
![Fedora](./img/fedora.png)
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
- Keep your `.pem` key file secure and never share it
- The username (e.g., `ubuntu`) may vary depending on your server's operating system
- Make sure your security group settings allow SSH access (port 22)

## Troubleshooting
- If you get a permission error, you may need to adjust your key file permissions
- Ensure you're using the correct username for your server
- Verify that your server's security group allows inbound SSH traffic
- Double-check that you're using the correct public IP address
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

             