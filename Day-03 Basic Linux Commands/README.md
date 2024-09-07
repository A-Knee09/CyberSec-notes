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

### 1. `pwd` : The where the hell am I command
- The pwd command in Linux stands for "print working directory." It is used to display the full path of the current directory you are in. This command helps you know exactly where you are in the directory structure at any given time. If you use the cd command to move to a different directory and want to confirm your new location, running pwd will show you the complete path of where you are.

    ![Screenshot 2024-09-07 002632](https://github.com/user-attachments/assets/1c90de0e-ba71-4eb4-9440-df7a35bd41dd)
   

 ### 2. `mkdir` : The make directory command 
 - The mkdir command in Linux is used to create new directories (folders). You can create one or multiple directories at once, and even create parent directories if they don't already exist.
 - To create a directory we can simply write `mkdir dir_name`.
 - We can also create a directory with space character by using single or double quotes. `mkdir 'dir name'`.
 - We can also create multiple directories at the same time. `mkdir dir-1 dir-2 dir-3 'dir 4' `.
 - We can create parent and child directories at the same time. `mkdir -p parent_dir/child_dir`.

   

   https://github.com/user-attachments/assets/9f4357da-f622-41f2-8473-be75ea74edfc




   
### 3. `cd` : The change directory command

- The cd command in Linux stands for "change directory." It is used to navigate between directories in the file system from the command line.Basically means going from one folder to another
- ```
  cd [directory name]
  ```
- For example I have a folder in my Desktop directory named as 'dir'. In order to go from Desktop Directory to dir directory I can simply write `cd dir`

  ![Screenshot 2024-09-07 003128](https://github.com/user-attachments/assets/736e6d33-3687-450a-9529-818405146569)

  > Please know that when we open terminal by default we are in our home `~` directory. For convinience purpose I'm already inside the Desktop dir.
   
- In order to go back to Desktop directory you can write `cd ..`.

  ![Screenshot 2024-09-07 003350](https://github.com/user-attachments/assets/dbead542-56b1-4fff-838d-ce6e418fc059)
  
- If a directory exist with spaces in it's name (for example 'dir 3' dir) we can write it as `cd 'dir 3'`.

  ![Screenshot 2024-09-07 003455](https://github.com/user-attachments/assets/efb7cb95-6ac3-43fd-b1c5-35518e48b849)

- In order to go back to the home directory we can simply write `cd` or `cd ~`. Whenever we open our terminal , by default we are in home directory

  ![Screenshot 2024-09-07 003959](https://github.com/user-attachments/assets/6155b67e-416c-430e-af04-6e05b715404a)

- To go to the root folder (`/`) simply write `cd /`

  ![Screenshot 2024-09-07 004043](https://github.com/user-attachments/assets/868b3aa2-3d2d-45e8-8149-67d191e72dc1)


- **Navigating using relative path** - If you are inside `/home/kali` and want to go to `home/Kali/Desktop/dir` you can write `cd Desktop/dir`.

  ![Screenshot 2024-09-07 004248](https://github.com/user-attachments/assets/366c07f9-8a5b-4459-a2d0-1889a6737fdf)

- **Using absolute path** : Giving an absolute path simply means giving the full address for the destination directory. For example if we are inside our dir 3 directory or any directory and we wanted to go to 'dir' directory we can write the absolute path for it `cd home/kali/Desktop/dir`. This way you can go to any directory without having to navigate tediously using relative path system.

  ![Screenshot 2024-09-07 004957](https://github.com/user-attachments/assets/e2b25dbf-09ea-45fa-bd36-9eb751ab3e88)

- **Navigating multiple levels up** : If you're in /home/Kali/Desktop/dir, writing `cd ../../` this command will take you to /home.

  ![Screenshot 2024-09-07 005101](https://github.com/user-attachments/assets/1004c7d6-2fff-40b0-a99c-7609a9fd81e9)

This covers the basics of `cd` command which would help you to navigate around your linux system
> [!TIP]
> whenever you write cd **directory name** if the directory name doesnt appear in bold letter then that means either you are writing the directory name wrong or the directory does not exist


### 3. `ls`: The list contents command 
- The ls command in Linux is used to list the contents of a directory. It displays files, directories, and other types of file system objects within the directory you specify. By default, ls lists the contents of the current directory, but you can also specify other directories. Syntax for ls :
   ```
  ls [options] [directory]
  ```
- You can write `ls --help` to open up the help section for ls command. This would display information about the ls commands and all the options the ls command comes with.

  ![Screenshot 2024-09-07 005338](https://github.com/user-attachments/assets/9122a7f9-f2c0-4670-9f94-746309f4620d)


- Lets say we are inside our home (`~`) folder and we wanted to see all the directories present inside our root folder. We can simply write `ls` to list all the directories present inside our root directory.

  ![Screenshot 2024-09-07 005514](https://github.com/user-attachments/assets/a5e25ba0-8b0c-4fb6-8970-93841a12e37b)

- **Including Hidden Files `ls -a`** : Some files may be hidden , in order to view those file we can write `ls -a' here -a stands for -all which is an option which allows us to list hidden files.The hidden files are denoted by "." preceeding them.

  ![Screenshot 2024-09-06 202255](https://github.com/user-attachments/assets/4de2def5-e0ed-4ca8-8885-9ce15a92964b)

  > Here I ran two ls commands, `ls` shows all the directories and files that arent hidden and `ls -a` shows files that are hidden, such as .icons , .themes , .local , etc.

- **Long list format `ls -l`** : The `ls -l` command provides a detailed listing of the files and directories in a directory, showing multiple attributes for each item.

  ![Screenshot 2024-09-06 222548](https://github.com/user-attachments/assets/c184ae63-4db2-4148-9d09-94f01264b01c)

  Here is what each column shows
  - File Type and Permissions :
      - The first character indicates the file type. `-` indicates its a regular file and  `d` indicates its a directory .
      - The next nine characters represent the permissions for the file, divided into three groups (owner, group, others). `r` is for read , `w` is for write and `x` is for execute.
      - for example `-rw-rw-r--` for file `hash.txt` says that owner can read and write the file , groups can read and write the file , and other users can only read the file.
 
  - Number of Links (e.g., 1 or 2): This number represents the hard link count. For directories, it shows the number of subdirectories and itself.
  - Owner (eg. user): The user who owns the file or directory.
  - Group : The group associated with the file or directory. Typically, this is the primary group of the owner.
  - File size: The size of the file in bytes. For directories, the size may refer to the size of the metadata (typically 4096 bytes).
  - Last Modification Time (e.g., Aug 12 12:00): The last date and time the file or directory was modified.Format: Month Day Hour:Minute.
  - File name (e.g., file1.txt or dir1): The name of the file or directory.

 - **Human readable format `ls -lh`**: Prints file sizes in human-readable format (e.g., 1K, 234M, 2G) , since it can be pretty difficult to understand bigger file sizes.
    
    ![Screenshot 2024-09-06 230102](https://github.com/user-attachments/assets/2e7ae30f-1d77-4684-acca-92ddd4541993)
   
    > You can combine multiple options to customize your output. For example, to get a detailed, human-readable list of all files, including hidden ones. `ls -lha`

> [!NOTE]
> A lot of options for ls exist as you can see in the `ls --help` menu. I have only listed some basic ones here to give a general understanding.

> [!IMPORTANT]
> You dont have to be inside a current directory to list their contents , you can also write `ls -option dir/file path`.

### `rmdir`: The remove directory command
- The rmdir command in Linux is used to remove **empty directories**. It only works on directories that do not contain any files or subdirectories. To delete a directory you have to be outside that directory , so make sure to check the file path you're in.
- The command can be used to remove a single directory. ``rmdir directory_name``.
- The command can be used to remove multiple directories. ```rmdir dir1 dir2 'dir 3'```.
- The command can be used parent/child directoriries using `-p` option. ```rmdir -p parent/child```.

  ![Animation](https://github.com/user-attachments/assets/c32869ac-9903-421e-82ce-2d364a5de1d3)

  
  

  
