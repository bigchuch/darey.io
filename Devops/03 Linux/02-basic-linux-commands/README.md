# Linux Commands Deep Dive

**Now that you have a client terminal and have accessed your remote server, what next?**  
For the next couple of projects, you will learn a lot about Linux commands, so it's time to get your hands dirty.

## What is a Linux Command?

A Linux command refers to a program or utility that runs in the command-line interface (CLI). The CLI is a text-based environment where you interact with the system by typing commands and receiving output.

Linux commands are executed by entering text into the terminal and pressing Enter. These commands enable you to perform a wide range of tasks, from managing files and directories to running programs and configuring the system.

### Basic Command Structure

The general syntax of a Linux command is as follows:
```
command [option(s)] [arguments]
```
A command may consist of options, arguments, and flags, but they are not always required. Here are the key components of a Linux command:

**Command Name**: This represents the action or task you want to perform using the command. For example, if you wish to list files in a folder, you basically use the `ls` command.

**Options or Flag**: An option modifies the behavior of a command. It is typically preceded by a hyphen (-) or double hyphen (--) and can be used to customize the command's functionality. For example, if I want to show extra information for each listed file, I will run the command `ls -l`.

**Parameters or Arguments:** A parameter provides specific information or data required by the command to execute the desired action. For example, if I want to create a new directory (or folder), I will use the `mkdir` command. The parameter will be the name of the directory which I will pass to it. 'mkdir photos' will create a **photos** directory.

It's important to note that Linux commands are case-sensitive, and the command name and its parameters should be typed exactly as they are written in the documentation or manual.

## Manipulating Files and Directories on Linux

Most of your time on Linux will be working with files and directories. Hence, it is very important to know how to work with them. In the next section, we will focus on different commands that cover different use cases of manipulating files and directories on Linux.

The `sudo` stands for `superuser do` and it allows you to run commands with the security privileges of another user, typically the superuser or `root`.

## Why Use `sudo`?

Using `sudo` (short for "superuser do") is essential for managing system-level tasks on Linux systems. Here's why:

- **Security:** It restricts access to powerful commands, reducing the risk of accidental or malicious system changes.
- **Tracking:** It logs each command executed with `sudo`, providing accountability and traceability.

## How `sudo` Works

When you prefix a command with `sudo`, the system prompts you for your password. Upon successful authentication, you gain temporary superuser privileges (typically for 15 minutes), allowing you to execute administrative commands without re-entering your password each time.

## Creating a Folder with `sudo`

In some directories, especially system-level ones like `/root`, you need elevated privileges to create files or folders. Here's how to do it:

1. Open your terminal and connect to your Linux server using SSH.  
2. Attempt to create a folder in a restricted location. For example, to create a folder named `example` in the `/root` directory:

   ```bash
    mkdir /root/example
   ```

3. You will receive a permission denied error message. This is because you don't have the necessary privileges to create files or folders in the `/root` directory.  
    ![img](/img/trying%20to%20make%20a%20dir%20in%20root%20folder.png)

4. To create the folder successfully using `sudo`, use the following command:
    ```bash
    sudo mkdir /root/example
    ```
    ![img](/img/succeful%20creation%20of%20folder%20using%20sudo.png)  
    This command uses `sudo` to grant the necessary permissions for folder creation in a protected directory.

    **Verify the folder's creation:** The command should succeed without errors. You can check the folder's existence by listing the content of the `/root` directory using the `ls` command. It should include the newly created folder in the output on the screen. Though you may need to use sudo again to view the contents of the directory:
    ```bash
    sudo ls /root
    ```

    **Note:** It's important to exercise caution when using `sudo` to avoid unintended system modifications. Always double-check the command and ensure you have the necessary permissions before executing administrative tasks.

    **Pwd command**

    Use the `pwd` command to display the current working directory.
    ```bash
    pwd
    /Users/bigchuch
    ```
    The Linux directory structure.

    After learning about the use of `sudo`, it's important to understand the Linux directory structure. Here's a brief overview of the most common directories:
    - **Home Directory (`~`):** Each user has their own home directory, typically located at `/home/username`. This is where users store their personal files and settings.
    - **Root Directory (`/`):** The root directory is the highest level in the Linux file system. It contains the system's core files and directories.
    - **System Configuration Files (`/etc`):** This directory contains system-wide configuration files. It's a crucial location for managing system settings and services.
    - **Binary executables** (/bin): This directory contains the binary executables for system commands.
    - **User-specific binaries** (/usr/bin): This directory contains user-specific binary executables.
    - **User-specific applications** (/usr/local/bin): This directory is used to install local applications and binaries.
    - **User-specific configuration files** (/home/username/.config): This directory stores user-specific configuration files.

    **`cd` command:** To navigate through Linux files and directories, use the `cd` command.

    Let's say you want to navigate the root filesystem on your server. Remember, the root filesystem is like the "C:" drive on a Windows computer. It is the starting point of folders and is represented by the forward slash `/`.  
    To navigate to the root filesystem, you can use the `cd` command followed by the forward slash `/`. Here's how to do it:

    To confirm that you are in the root filesystem, you can use the `pwd` command.
    ```bash
    sudo cd /
    ```
    ![img](/img/cd%20&%20pwd.png)

    To list the files in the current directory, you can use the `ls -l` command.
    ```bash
    ls
    ```
    Below is the output of the ls command  
    ![img](/img/list%20of%20file%20directory%20.png)

    If you want to navigate to any of the directories in the output, let's say the `usr` directory, you can use the `cd` command followed by the directory name. Here's how to do it:
    ```bash
        cd /usr
    ```
    ## Let's create a side task
    * Create a directory called `photos` inside the `/usr` directory.
    * Navigate to the `photos` directory.
    * Create 3 more random directories inside the `photos` directory.
    * Show the new created directories on the terminal.
    * Navigate into one of them.
    * Show the full path where you currently are on the screen.  
    ![img](/img/side%20task%20.png)

    **The `ls` command:** List files and directories. Running it without a flag or parameter will display a list of files and directories in the current working directory.

    To see other directories' content, type `ls` followed by the directory name. For example, to see the contents of the `/root` directory, type:
    ```bash
    ls /root
    ``` 
    Here are some options you can use with the `ls` command:

    ```
    ls -R (recursive): This option lists subdirectories and their contents recursively.

    ls -a (all): This option displays all files and directories, including hidden ones (those starting with a dot).

    ls -lh (long format with human-readable file sizes): This option displays detailed information about each file or directory, including permissions, ownership, and file size in a human-readable format.
    ```
    **cat command**  
    **`Concatenate`**, or `cat`, is a command-line utility in Linux that is used to display the contents of one or more text files on the terminal. It is commonly used to read and display the contents of text files, such as configuration files, log files, or any other text-based data.  
    Here's the basic syntax of the `cat` command:
    ```bash
        sudo cat /etc/os-release
    ```
    Displays the content of the `os-release` file in the `/etc` directory.  
    ![img](/img/cat%20comand%20.png)

    **cp command**

    Use the `cp` command to copy files and directories and their content. Take a look at the following use cases:  
    To copy one file from the current directory, enter `cp` followed by the name of the file you want to copy and the destination path. For example, to copy the file `example.txt` to the `/home/ubuntu/Documents` directory, enter:
    ```bash
        cp example.txt /home/ubuntu/Documents/
    ```
    This will copy `example.txt` to the `Documents` directory.  
    ![img](/img/copy%20files%20cp%20command.png)

    To copy multiple files, enter the `cp` command followed by the names of the files you want to copy and the destination path. For example, to copy the files `example1.txt` and `example2.txt` to the `/home/ubuntu/Documents` directory, enter:
    ```bash
    cp example1.txt example2.txt /home/ubuntu/Documents/
    ```
    To copy the content of a file to another file, enter the `cp` command followed by the name of the source file and the name of the destination file. For example, to copy the content of `example.txt` to `new_example.txt`, enter:

    ```bash
    cp example.txt new_example.txt
    ```
    To copy an entire directory, use the `cp` command followed by the `-r` flag, the name of the source directory, and the destination path. For example, to copy the `Documents` directory to the `/home/ubuntu` directory, enter:

    ```bash
        cp -r Documents /home/ubuntu/
    ```
    **mv command**

    The primary use of the `mv` command is to move files and directories. It is used to rename files and directories, or to move them to different locations.  
    To rename a file, enter the `mv` command followed by the name of the file you want to rename and the new name you want to give it. For example, to rename the file `example.txt` to `new_example.txt`, enter:
    ```bash
    mv example.txt new_example.txt
    ```
    To move a file to a different directory, enter the `mv` command followed by the name of the file you want to move and the destination path. For example, to move the file `example.txt` to the `/home/ubuntu/Documents` directory, enter:
    ```bash
    mv example.txt /home/ubuntu/Documents/
    ```
    ![img](/img/move%20file%20from%20one%20folder%20to%20another.png)

    **rm command**

    The `rm` command is used to delete files within a directory.

    **Caution:** This is a very dangerous command as it deletes the files completely. So it must be used with care.

    To remove a single file:
    ```bash
    rm filename
    ```
    To remove multiple files, enter the following command:
    ```bash
        rm filename1 filename2 filename3
    ```

    ![img](/img/deleting%201%20file%20and%20multiple%20files.png)

    Here are some acceptable options you can add:

    ```bash
    -i prompts system confirmation before deleting a file. (Denotes "interactive")
    -f allows the system to remove without a confirmation. (Denotes "force")
    -r deletes files and directories recursively.
    ```

    **touch command**  
    The `touch` command allows you to create an empty file.

    For example, enter the following command to create an HTML web file in the Documents directory:
    ```bash
    touch /home/ubuntu/Documents/Web.html
    ```
    ![img](/img/touch%20command%20.png)

    **find command**  
    Use the `find` command to search for files within a specific directory and perform subsequent operations. Here's the general syntax:

    ```bash
    find [option] [path] [expression]
    ```
    For example, to look for a file named **notes.txt** within a folder and its subfolders:
    ```bash
    find /home -name notes.txt
    ```
    ![img](/img/find%20commad.png)