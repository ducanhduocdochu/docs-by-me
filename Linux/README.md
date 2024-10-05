# 📜 Linux Commands Cheat Sheet

> **A comprehensive guide of Linux commands for quick reference.**

---

## 📂 **File and Directory Operations**
- **`pwd`**: Prints the current working directory path.
  - **Example**: 
    Imagine you're navigating through various folders in a Linux system. If you ever get lost and want to know exactly where you are, use `pwd` to show your current location in the file system.
    ```bash
    $ pwd
    /home/ducanh/Documents/Projects
    ```
    In this case, you're inside the "Projects" folder, which is located under "Documents", in the "home" directory of the user "ducanh".
- **`whoami`**: Display the current logged-in user.
  - **Example**: 
    When you're working on a Linux system with multiple users, you might want to check which user you're currently logged in as. The `whoami` command gives you that information instantly.
    ```bash
    $ whoami
    ducanh
    ```
    In this example, the system responds with "ducanh", indicating that you are logged in as the user "ducanh".
- **`cd`**: Change directory.
  - **Example**: 
    If you want to navigate to a different directory in your file system, use `cd` followed by the path of the directory you want to move to. For instance, if you're currently in your home directory (`/home/ducanh`), and you want to move to the "Documents" folder, you can run:
    ```bash
    $ cd Documents
    ```
    Now, you are inside `/home/ducanh/Documents`. To go back to the parent directory (your home folder), you can simply run:
    ```bash
    $ cd ..
    ```
    This moves you back to `/home/ducanh`.
  - **Tip**: If you're not sure where you are in the directory structure, you can combine `cd` with `pwd` to check your current location after moving:
    ```bash
    $ cd /home/ducanh/Projects
    $ pwd
    /home/ducanh/Projects
    ```
- **`ls`**: List files and directories.
  - **Example**: 
    Suppose you are working in the `/home/ducanh/Documents` directory and wants to see the files and directories available. He can simply type:
    ```bash
    $ ls
    ```
    This will list all the files and directories in that folder.

    To show **hidden files** (files that start with a dot `.`), you can use the `-a` option:
    ```bash
    $ ls -a
    ```
    This command will display hidden files like `.gitignore` in addition to regular files.

    If you wants to list files **sorted by the most recently modified** (newest first), he can use the `-t` option:
    ```bash
    $ ls -t
    ```
    Files and directories will be shown in order of last modification time, with the most recently modified ones at the top.

    For a **detailed list** that shows file permissions, ownership, size, and modification date, you can use the `-l` option:
    ```bash
    $ ls -l
    ```
    This provides a long listing format, showing more detailed information for each file and directory.
- **`mkdir <directory_name>`**: Create a directory.
  - **Example**: 
    You can organizing his projects and wants to create a new directory called "NewProject" in his `Documents` folder. You can use:
    ```bash
    $ mkdir NewProject
    ```
    Now, a directory named `NewProject` is created inside `/home/ducanh/Documents`.

    If you need to create multiple nested directories at once, such as `Projects/Web/Frontend`, you can use the `-p` option to create **parent directories as needed**:
    ```bash
    $ mkdir -p Projects/Web/Frontend
    ```
    This command will create the entire directory structure (`Projects`, `Web`, and `Frontend`) in one go, even if `Projects` and `Web` didn't exist before.

- **`touch <filename>`**: Create an empty file or update file timestamp.
  - **Example**: 
    You are working on a new project and needs to create a blank file called `README.md` in his project folder. You can use the `touch` command to create the file:
    ```bash
    $ touch README.md
    ```
    Now, an empty file named `README.md` is created inside your current directory.

    If You wants to **update the timestamp** of an existing file, such as `index.html`, he can run:
    ```bash
    $ touch index.html
    ```
    This command will not modify the content of the file but will update its last modification time to the current time.

- **`rm <file>`**: Remove a file.
  - **Example**: 
    You have finished working on a temporary file called `temp.txt` and wants to delete it. You can use the `rm` command:
    ```bash
    $ rm temp.txt
    ```
    This command will remove the `temp.txt` file from the current directory.

- **`rm -r <directory>`**: Remove a directory and its contents recursively.
  - **Example**: 
    You realize you no longer needs a directory called `OldProjects` and wants to delete it along with all its contents. You can use:
    ```bash
    $ rm -r OldProjects
    ```
    This command will delete the `OldProjects` directory and all files and subdirectories within it.

- **`rm -rf <directory>`**: Force remove a directory without asking.
  - **Example**: 
    If you are sure you wants to delete a directory named `Archive` without any confirmation prompts, you can use the `-rf` options together:
    ```bash
    $ rm -rf Archive
    ```
    This command will remove the `Archive` directory and everything inside it immediately, without asking for confirmation.

- **`cp <source> <destination>`**: Copy files or directories.
  - **Example**: 
    You want to make a backup of his `project.zip` file. You can use the `cp` command to copy it to a backup folder called `Backup`:
    ```bash
    $ cp project.zip Backup/
    ```
    This command creates a copy of `project.zip` in the `Backup` directory.

- **`cp -r <source_directory> <destination_directory>`**: Copy directories recursively.
  - **Example**: 
    If you want to copy an entire directory called `Images` to the `Backup` directory, you can run:
    ```bash
    $ cp -r Images Backup/
    ```
    This command will copy the `Images` directory along with all its contents into the `Backup` directory.

- **`mv <source> <destination>`**: Move files or directories, or rename them.
  - **Example**: 
    You decides to rename your file `draft.txt` to `final.txt` and move it to the `Documents` directory:
    ```bash
    $ mv draft.txt Documents/final.txt
    ```
    This command renames and moves `draft.txt` to the `Documents` folder as `final.txt`.

- **`cat <filename>`**: Display content of a file.
  - **Example**: 
    If you want to view the contents of your `notes.txt` file, you can use:
    ```bash
    $ cat notes.txt
    ```
    This will display the entire content of `notes.txt` in the terminal.

- **`echo "text" > <filename>`**: Write text to a file (overwriting).
  - **Example**: 
    You want to add a header to his `README.md` file. you can write "Project Title" into the file using:
    ```bash
    $ echo "Project Title" > README.md
    ```
    This command will create (or overwrite) the `README.md` file with the text "Project Title".

- **`tail -n 1 <filename>`**: Display the last line of a file.
  - **Example**: 
    To see the most recent entry in your `log.txt` file, you can run:
    ```bash
    $ tail -n 1 log.txt
    ```
    This will display the last line of `log.txt`.

- **`tail -f <filename>`**: Monitor file for real-time updates.
  - **Example**: 
    You want to watch real-time updates to your `server.log` file as it gets written to. You can use:
    ```bash
    $ tail -f server.log
    ```
    This command will keep the terminal open and display new entries in `server.log` as they are added.


---

## 🖥️ **System Monitoring and Management**

- **`free -m`**: Check memory usage (in MB).
  - **Example**: 
    If you want to check how much memory is currently being used on your system, you can run:
    ```bash
    $ free -m
    ```
    This command will display memory usage statistics in megabytes, showing total, used, free, and cached memory.

- **`df -h /`**: Check disk space usage in human-readable format.
  - **Example**: 
    To see how much disk space is available on your root filesystem, you can use:
    ```bash
    $ df -h /
    ```
    This command provides a summary of disk space usage with human-readable sizes, showing total space, used space, available space, and mount point.

- **`hostnamectl set-hostname <new_hostname>`**: Change the system hostname.
  - **Example**: 
    If you want to change your system's hostname to `my-server`, you can execute:
    ```bash
    $ hostnamectl set-hostname my-server
    ```
    This command will set your system's hostname to `my-server`, which can be helpful for identifying the machine on a network.

- **`reboot`**: Restart the system.
  - **Example**: 
    After making changes to the system or applying updates, you might need to restart your computer. You can do this by typing:
    ```bash
    $ reboot
    ```
    This command will restart your system immediately.

- **`netstat -tlpun`**: Show active network connections and listening ports.
  - **Example**: 
    To see which ports are currently open and which applications are using them, you can use:
    ```bash
    $ netstat -tlpun
    ```
    This command displays a list of listening ports along with the corresponding process IDs (PIDs) and program names.

- **`ps`**: View running processes.
  - **Example**: 
    If you want to see all the currently running processes, you can run:
    ```bash
    $ ps
    ```
    This will display a list of processes running in your current terminal session.

  - **`ps aux`**: Detailed information about running processes.
    - **Example**: 
      For more detailed information about all processes running on the system, including CPU and memory usage, you can use:
      ```bash
      $ ps aux
      ```
      This command provides a comprehensive view of all running processes, showing the user, PID, CPU usage, memory usage, and command.

- **`top`**: Real-time view of system processes and resource usage.
  - **Example**: 
    To monitor system performance in real-time, you can use:
    ```bash
    $ top
    ```
    This command will open an interactive terminal interface displaying real-time information about system processes, including CPU usage, memory usage, and process IDs. You can press `q` to exit the `top` interface.

---

## 🌐 **Network Commands**

- **`ping <hostname/IP>`**: Test connectivity to a server.
  - **Example**: 
    If you want to check if a server is reachable, you can use the `ping` command. For example, to test connectivity to `google.com`, run:
    ```bash
    $ ping google.com
    ```
    This command will send packets to `google.com` and display the response times, helping you determine if the server is reachable and how long it takes to respond.

- **`telnet <hostname> <port>`**: Check connectivity to a remote server and port.
  - **Example**: 
    To check if a specific service is running on a remote server, such as HTTP on port 80, you can use:
    ```bash
    $ telnet example.com 80
    ```
    If the connection is successful, you will see a blank screen, indicating that you can connect to the server on that port. If the service is not available, it will show an error message.

- **`traceroute <IP>`**: Trace the route packets take to a remote IP.
  - **Example**: 
    To see the path that packets take to reach a specific IP address, you can use the `traceroute` command. For example, to trace the route to `8.8.8.8` (Google's public DNS), you would run:
    ```bash
    $ traceroute 8.8.8.8
    ```
    This command will display each hop along the way, showing the routers that the packets pass through and their response times.

- **`traceroute -T -p 80 <IP>`**: Trace route using TCP on port 80.
  - **Example**: 
    If you want to trace the route to a server using TCP packets instead of the default ICMP, and specifically check the HTTP service on port 80, you can run:
    ```bash
    $ traceroute -T -p 80 example.com
    ```
    This command will trace the route to `example.com` using TCP packets directed at port 80, which is useful for checking web server connectivity specifically.

---

## 📦 **Package Management**

- **`apt install <package_name>`**: Install a package.
  - **Example**: 
    If you want to install the popular text editor `vim`, you can use the following command:
    ```bash
    $ sudo apt install vim
    ```
    This command will download and install the `vim` package from the repositories to your system.

- **`apt remove <package_name>`**: Remove a package.
  - **Example**: 
    If you no longer need `vim` and want to remove it from your system, you can run:
    ```bash
    $ sudo apt remove vim
    ```
    This command will uninstall the `vim` package while keeping its configuration files.

- **`apt update`**: Update package list from repositories.
  - **Example**: 
    Before installing or upgrading any packages, it’s a good practice to update the package list. You can do this by running:
    ```bash
    $ sudo apt update
    ```
    This command fetches the latest package lists from the repositories, ensuring that you have the most up-to-date information on available packages.

- **`apt upgrade`**: Upgrade all installed packages to the latest version.
  - **Example**: 
    After updating the package list, you can upgrade all installed packages to their latest versions by using:
    ```bash
    $ sudo apt upgrade
    ```
    This command will prompt you to confirm the upgrades and then proceed to update all the packages installed on your system.

---

## 👥 **User and Group Management**

- **`useradd <username>`**: Add a new user.
  - **Example**: 
    To add a new user named `john`, you can use:
    ```bash
    $ sudo useradd john
    ```
    This command creates a new user account named `john` without setting a password.

- **`adduser <username>`**: Add a new user (interactive mode).
  - **Example**: 
    If you prefer an interactive way to create a user, you can run:
    ```bash
    $ sudo adduser john
    ```
    This command will prompt you for additional information, such as the password and user details, making it easier to set up the user account.

- **`deluser <username>`**: Delete a user.
  - **Example**: 
    To remove the user `john` from the system, you can use:
    ```bash
    $ sudo deluser john
    ```
    This command will delete the user account `john`, but it will not remove the user's home directory.

- **`groupadd <groupname>`**: Create a new group.
  - **Example**: 
    If you want to create a new group named `developers`, you can run:
    ```bash
    $ sudo groupadd developers
    ```
    This command will create a new group called `developers`, which can be used for organizing user permissions.

- **`delgroup <groupname>`**: Delete a group.
  - **Example**: 
    To delete the `developers` group, you can execute:
    ```bash
    $ sudo delgroup developers
    ```
    This command will remove the group named `developers` from the system.

- **`usermod -aG <groupname> <username>`**: Add user to a group.
  - **Example**: 
    If you want to add the user `john` to the `developers` group, you can run:
    ```bash
    $ sudo usermod -aG developers john
    ```
    This command adds `john` to the `developers` group, allowing him to have group permissions.

- **`chown -R <user>:<group> <directory>`**: Change ownership of a file or directory.
  - **Example**: 
    To change the ownership of the `project` directory to user `john` and group `developers`, use:
    ```bash
    $ sudo chown -R john:developers project/
    ```
    This command recursively changes the ownership of all files and subdirectories within `project` to `john` and the `developers` group.

- **`chmod u=rx,g=rwx,o=- <directory>`**: Change permissions for a file or directory.
  - **Example**: 
    If you want to set specific permissions on the `project` directory so that the owner has read and execute permissions, the group has read, write, and execute permissions, and others have no permissions, you can run:
    ```bash
    $ sudo chmod u=rx,g=rwx,o=- project/
    ```
    This command sets the permissions as specified, which is crucial for controlling access to files and directories.

---

## 📂 **File Search and Archiving**

- **`find <path> -name <filename>`**: Search for files by name.
  - **Example**: 
    If you want to find a file named `report.txt` in the `/home/ducanh` directory, you can use:
    ```bash
    $ find /home/ducanh -name report.txt
    ```
    This command will search recursively through the specified directory and its subdirectories for any files that match the name `report.txt`.

- **`grep <pattern> <filename>`**: Search for a pattern inside a file.
  - **Example**: 
    To find all occurrences of the word "error" in the `log.txt` file, you can run:
    ```bash
    $ grep "error" log.txt
    ```
    This command will display all lines in `log.txt` that contain the word "error", making it easy to identify issues in log files.

- **`tar -cvf <archive_name.tar> <directory>`**: Create a tarball from a directory.
  - **Example**: 
    If you want to create an archive named `backup.tar` from the `project` directory, you can execute:
    ```bash
    $ tar -cvf backup.tar project/
    ```
    This command will create a tarball called `backup.tar` containing all the files and subdirectories in the `project` directory.

- **`zip -r <archive_name.zip> <directory>`**: Compress a directory into a zip file.
  - **Example**: 
    To compress the `project` directory into a zip file named `project.zip`, you can run:
    ```bash
    $ zip -r project.zip project/
    ```
    This command will create a zip archive called `project.zip`, which includes all files and folders within the `project` directory, making it easier to share or store.

---

## 📝 **Additional Useful Commands**

- **`uname -a`**: Display system information.
  - **Example**: 
    To get detailed information about your system, including the kernel version and architecture, you can run:
    ```bash
    $ uname -a
    ```
    This command will display output similar to:
    ```
    Linux ducanh 5.4.0-42-generic #46-Ubuntu SMP Thu Oct 8 08:12:45 UTC 2020 x86_64 x86_64 x86_64 GNU/Linux
    ```
    This gives you insights into the operating system and hardware specifications.

- **`dmesg`**: Show system boot and hardware messages.
  - **Example**: 
    To view the kernel ring buffer messages, which include system boot messages and hardware initialization, you can use:
    ```bash
    $ dmesg
    ```
    This command will display a list of messages logged by the kernel, helping you diagnose hardware-related issues or boot problems.

- **`htop`**: Interactive process viewer (if installed).
  - **Example**: 
    If you want a more user-friendly way to monitor system processes, you can run:
    ```bash
    $ htop
    ```
    This command opens an interactive terminal interface where you can see CPU, memory usage, and running processes. You can also sort and filter processes easily, making it a powerful tool for system monitoring.

---

📝 **Created by ducanhduocdochu**
