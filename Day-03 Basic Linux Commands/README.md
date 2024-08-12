# Basic Linux Commands

## Linux File Structure

  Before getting into linux commands let's try to understand the linux file structure. Understanding the file structure helps us to navigate around the system and gather information easily.
  
  ![standard-unix-filesystem-hierarchy-1500x826](https://github.com/user-attachments/assets/3355919c-fa51-4f30-ab9d-cbf2418f11b2)

  The Linux file system is a hierarchical directory structure that organizes files and directories in a way that is both intuitive and powerful. Here’s an overview of the key components and concepts:

### 1. **Root Directory (`/`):**
   - The root directory is the top level of the Linux file system hierarchy. All other directories and files stem from this point. The root directory is represented by a single forward slash (`/`).

### 2. **Key Directories Under Root:**
   - **`/bin`:** Contains essential binary executables needed for the system to function, such as common command-line tools (`ls`, `cp`, `mv`, etc.).
   - **`/sbin`:** Similar to `/bin`, but contains system binaries intended mainly for the system administrator (`ifconfig`, `reboot`, etc.).
   - **`/etc`:** Stores system-wide configuration files and shell scripts that are used to boot the system and configure various programs.
   - **`/home`:** Contains the home directories of individual users. For example, the user `john` would have a home directory at `/home/john`, where personal files and settings are stored.
   - **`/root`:** This is the home directory for the root user (the superuser), which is separate from the `/home` directory to ensure the root user’s files are isolated.
   - **`/var`:** Stands for variable files, and stores files that are expected to grow in size, such as logs (`/var/log`), mail, and print spool files.
   - **`/tmp`:** Stores temporary files created by various programs. These files are usually deleted upon system reboot.
   - **`/usr`:** Contains user programs and utilities. It’s further subdivided into directories like `/usr/bin` for user binaries, `/usr/sbin` for system binaries not critical for booting, `/usr/lib` for libraries, etc.
   - **`/opt`:** Used for the installation of additional software packages. It’s typically used by third-party applications.
   - **`/mnt` and `/media`:** These directories are used for mounting filesystems, such as external drives, CD-ROMs, and network shares.
   - **`/dev`:** Contains device files, which are not actual files but interfaces to the hardware components (like hard drives, USB devices, etc.).
   - **`/proc`:** A pseudo-filesystem that provides an interface to kernel data structures. It's used to access system information and configuration.
   - **`/sys`:** Similar to `/proc`, it provides information about the system and allows interaction with the hardware.

### 3. **File Types:**
   - **Regular Files:** These are the most common types of files that contain data, such as text files, images, and executables.
   - **Directories:** Special files that contain other files and directories.
   - **Symbolic Links:** Pointers to other files or directories.
   - **Special Files:** These include block devices, character devices, sockets, and named pipes (FIFO).

### 4. **Permissions and Ownership:**
   - Each file and directory has associated permissions that determine who can read, write, or execute the file. Permissions are divided into three categories: owner, group, and others.
   - **Ownership:** Every file and directory is owned by a user and a group, and these ownership attributes determine the permissions applied.

### 5. **Hierarchy and Navigation:**
   - The Linux filesystem is structured as a tree, starting from the root directory and branching out into subdirectories. Users navigate through this structure using commands like `cd` (change directory), `ls` (list directory contents), and others.

### 6. **FHS (Filesystem Hierarchy Standard):**
   - The FHS defines the directory structure and directory contents in Unix-like operating systems, ensuring consistency across different distributions.

Understanding the Linux file system is crucial for managing a Linux system, as it affects everything from user data management to system administration and application configuration.

## Linux Commands
- Linux commands are text-based instructions used to perform various tasks on a Linux operating system through the terminal.
- These commands range from basic operations like navigating directories to complex tasks like process management and network configuration.
- commands are written in the format
  
  ```
  command -option
  ```
> [!IMPORTANT]
> Linux commands and directories are case sensitive , so make sure you are careful about case sensitivity while using Command line interface.

## Basic Linux Commands

### 1. `cd` command

- The cd command in Linux stands for "change directory." It is used to navigate between directories in the file system from the command line.
- Basically means going from one folder to another
- ```
  cd [directory name]
  ```
- For example I have two folders in my Desktop directory named as 'ani' and 'Folder 1'. In order to go from Desktop Directory to ani directory I can simply write cd ani
  
  ![Inside ani dir](https://github.com/user-attachments/assets/d55ba190-f7ee-41a5-9271-1a32c1049b45)


- In order to go back to Desktop directory you can write `cd ..`

  ![Back to Desktop Dir](https://github.com/user-attachments/assets/4132850b-6f8c-4351-ac04-e3a30d2e77be)

- If a directory exist with spaces in it's name (for example 'Folder 2' dir) we can write it as `cd 'Folder 2'`

  ![Screenshot 2024-08-12 123003](https://github.com/user-attachments/assets/8bc2e330-96e4-4349-b640-6b2a9daca79d)
  > Error on line 3 since the name of the dir is 'Folder 2' and not 'folder 2' (case sensitive).
- In order to go back to the home directory we can simply write `cd` or `cd ~`
  
  ![back to home directory (~)](https://github.com/user-attachments/assets/159b724e-b647-4abb-a09d-3a8d03516d0f)

  > Whenever we open our terminal , by default we are in home directory

- To go to the root folder simply write `cd /`
  
  ![Inside root directory ()](https://github.com/user-attachments/assets/47a79434-f69d-4b1e-ad5b-11c0c09fb575)

- **Navigating using relative path** - If you are inside `/home/kali` and want to go to `home/Kali/Desktop/ani` you can write `cd /Desktop/ani'.

  ![Screenshot 2024-08-12 132744](https://github.com/user-attachments/assets/01f5fc8e-79f4-4c24-89a9-e418d9aa99b9)


- **Using absolute path** : Giving an absolute path simply means giving the full address for the destination directory. For example if we are inside our root directory or any directory and we wanted to go to 'ani' directory we can write the absolute path for it `cd home/kali/Desktop/ani`. This way you can go to any directory without having to navigate tediously using relative path system.

  ![Screenshot 2024-08-12 131449](https://github.com/user-attachments/assets/8e57661e-13b2-4ca6-8064-f8057d29e34e)

- **Navigating multiple levels up** : If you're in /home/Kali/Desktop/ani, writing `cd ../../ this command will take you to /home.

  ![Screenshot 2024-08-12 132115](https://github.com/user-attachments/assets/65569bc2-45ea-458a-93f4-b749a01fcef5)

This covers the basics of `cd` command which would help you to navigate around your linux system
> [!TIP]
> whenever you write cd **directory name** if the directory name doesnt appear in bold letter then that means either you are writing the directory name wrong or the directory does not exist

### 2. `pwd` command
- The pwd command in Linux stands for "print working directory." It is used to display the full path of the current directory you are in. This command helps you know exactly    where you are in the directory structure at any given time.

  ![Screenshot 2024-08-12 135054](https://github.com/user-attachments/assets/9a918ee2-e741-4747-b2d5-e1593b127300)

- If you use the cd command to move to a different directory and want to confirm your new location, running pwd will show you the complete path of where you are.

  ![Screenshot 2024-08-12 135331](https://github.com/user-attachments/assets/4239fdaf-92d7-461b-8ea8-51fdd5aef278)

### 3. `ls` command 
- The ls command in Linux is used to list the contents of a directory. It displays files, directories, and other types of file system objects within the directory you specify. By default, ls lists the contents of the current directory, but you can also specify other directories.
- Syntax for ls :
   ```
  ls [options] [directory]
  ```
- You can write `ls --help` to open up the help section for ls command. This would display information about the ls commands and all the options the ls command comes with.

  ![Screenshot 2024-08-12 141627](https://github.com/user-attachments/assets/99bb2352-ef05-4d1b-8ee5-87a4071ca77c)

- Lets say we are inside our root folder by using the command `cd /` and we wanted to see all the directories present inside our root folder. We can simply write `ls` to list all the directories present inside our root directory.

  ![Screenshot 2024-08-12 140413](https://github.com/user-attachments/assets/9290055f-058b-4666-928a-57cd975f75c2)

- ***Including Hidden Files** : Some files may be hidden , in order to view those file we can write `ls -a' here -a stands for -all which is an option which allows us to list hidden files.

  
