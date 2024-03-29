# 01-GCKL

- **GETTING COMFORTABLEWITH KALI LINUX**

## **☠️ Kali Linux**

### **Kali Linux is a Debian-derived Linux distribution designed for digital forensics and penetration testing. It is maintained and funded by Offensive Security**

### **Download Kali (Kali Linux 64-bit VMware)**

[Get Kali | Kali Linux](https://www.kali.org/get-kali/#kali-virtual-machines)

### **👀 Checksum**

- Verifying SHA256 Checksum of a File in Linux
    - 📝Note :
        - The computer software that is used to validate and calculate the SHA-1 hashes is known as sha1sum. SHA-1 stands for Secure Hash Algorithm
        - The SHA-256 standard is used in document integrity checks. It's preferred over the SHA-1 standard since the latter has been shown to produce the same hash for different documents.
        - `-a` option is used to specify the algorithm that should be used to generate the checksum.
        - The `256` option specifies that the SHA-256 algorithm should be used.
    
    ```bash
    ┌──(kali㉿kali)-[~]
    └─$ shasum -a 256 kali-linux-2023.3-vmware-amd64.7z
    **cda70**1776d4e17c24845c0b2d57e40f4fecab5c7de22d88ddc7bdaef671**b0838**
    ```
    

### 🖥️ Virtual Machine

- In computing, a virtual machine is the virtualization or emulation of a computer system. Virtual machines are based on computer architectures and provide the functionality of a physical computer. **Their implementations may involve specialized hardware, software**, or a combination of the two.
- **The most common virtual machines for Windows, Mac, and Linux are:**
    - VMware Workstation
    - VMware Fusion
    - VirtualBox
    - QEMU/KVM
    - Hyper-V

### 📀**Launch a Linux Virtual Machine**

- To open and launch the extracted **VM**, open a file manager window, navigate to the directory containing the extracted files, and double-click the **.vmx** file.
    
    ![mceclip3.png](00-assets/mceclip3.png)
    
- As the virtual machine is starting up, VMware will display a prompt asking if you moved or copied the **VM**. Click the "I Copied It" button to continue.

![lin-moved-or-copied1.png](00-assets/lin-moved-or-copied1.png)

- Once the VM has been booted, you can log in with the username of k**ali** and the password of k**ali**.
- Make sure you change the default password with the **passwd** command after you have logged in.

### 💻 Kali Linux Undercover Mode

- To make **Kali Linux** → look like Windows

```bash
┌──(kali㉿kali)-[~]
└─$ kali-undercover
```

![Screenshot 2023-10-03 073515.png](00-assets/Screenshot_2023-10-03_073515.png)

### 🤔 Why Kali Linux Not Windows

- Kali Linux is open-source, which means that the code is freely available and auditable. This is important for security testing, as it allows testers to verify that the tools they are using are secure.

![sxb7zfdcghy4trvui2mk.jpeg](00-assets/sxb7zfdcghy4trvui2mk.jpeg)

- Kali Linux is designed for security testing, and it comes pre-installed with a wide range of tools and utilities for this purpose. This saves testers the time and hassle of having to install and configure these tools themselves.
- Kali Linux is lightweight and can be run on a variety of hardware, including laptops and virtual machines. This makes it easy for testers to deploy Kali Linux where they need it.

### 🪄 Your first Linux Command

- **ls** → for List: It is used to **list all the files and directories under a specified directory**
- Show this **code**
    
    ```bash
    ┌──(kali㉿kali)-[~]
    └─$ ls
    Desktop   Downloads   Music   Public    Templates   Documents   Pictures  Videos
    ```
    
- **cd** → for **Change Directory**: It is used to change the current directory of the terminal
- Show this **code**
    
    ```bash
    ┌──(kali㉿kali)-[~]
    └─$ cd Downloads
    ┌──(kali㉿kali)-[~/Downloads]
    └─$
    ```
    
- If you want to go back one step, use this → **cd ..**
- Show this **code**
    
    ```bash
    ┌──(kali㉿kali)-[~/Downloads]
    └─$ cd ..
    ┌──(kali㉿kali)-[~]
    └─$
    
    ```
    
- **clear** or **ctrl+l** → for **clear** our terminal
- Show this **code**
    
    ```bash
    ┌──(kali㉿kali)-[~/Downloads]
    └─$ cd ..
    ┌──(kali㉿kali)-[~]
    └─$
    ┌──(kali㉿kali)-[~]
    └─$ ls
    Desktop   Downloads   Music   Public    Templates   Documents   Pictures  Videos
    ┌──(kali㉿kali)-[~]
    └─$ clear
    ```
    
    - **result :**
    
    ```bash
    ┌──(kali㉿kali)-[~]
    └─$
    ```
    

### 📂 Linux File System

- **/**
    - `The /` in the instruction above refers to the ***root*** directory. The **root directory** is the one from which all other directories branch off from
    - *show me only the 1st Level of the directory tree starting at / (**root**)*
        
        ```bash
        ┌──(kali㉿kali)-[~]
        └─$ tree / -L 1
        /
        ├── bin -> usr/bin
        ├── boot
        ├── dev
        ├── etc
        ├── home
        ├── initrd.img -> boot/initrd.img-6.1.0-kali9-amd64
        ├── initrd.img.old -> boot/initrd.img-6.1.0-kali5-amd64
        ├── lib -> usr/lib
        ├── lib32 -> usr/lib32
        ├── lib64 -> usr/lib64
        ├── libx32 -> usr/libx32
        ├── lost+found
        ├── media
        ├── mnt
        ├── opt
        ├── proc
        ├── root
        ├── run
        ├── sbin -> usr/sbin
        ├── srv
        ├── sys
        ├── tmp
        ├── usr
        ├── var
        ├── vmlinuz -> boot/vmlinuz-6.1.0-kali9-amd64
        └── vmlinuz.old -> boot/vmlinuz-6.1.0-kali5-amd64
        
        23 directories, 4 files
        
        ┌──(kali㉿kali)-[~]
        └─$
        ```
        
- ***/bin***
    - Unlike /sbin, the bin directory contains several useful commands that are of use to both the system administrator as well as non-privileged users.
    - It usually contains shells like bash, csh, etc.... and commonly used commands like cp, mv, rm, cat, ls. For this reason and in contrast to /usr/bin, the binaries in this directory are considered to be essential
- **/etc**
    - This is the nerve center of your system, it contains all system related configuration files in here or in its sub-directories. A "configuration file" is defined as a local file used to control the operation of a program;
    - it must be static and cannot be an executable binary. For this reason, it's a good idea to backup this directory regularly.
    - It will definitely save you a lot of re-configuration later if you re-install or lose your current installation. Normally, no binaries should be or are located here.
- **/sbin**
    - Linux discriminates between 'normal' executables and those used for system maintenance and/or administrative tasks. The latter reside either here or - the less important ones - in /usr/sbin. Locally installed system administration programs should be placed into /usr/local/sbin.
    - Programs executed after /usr is known to be mounted (when there are no problems) are generally placed into /usr/sbin. This directory contains binaries that are essential to the working of the system. These include system administration as well as maintenance and hardware configuration programs. You may find lilo, fdisk, init, ifconfig, etc.... here.
- **/tmp**
    - This directory contains mostly files that are required temporarily. Many programs use this to create lock files and for temporary storage of data.
    - Do not remove files from this directory unless you know exactly what you are doing! Many of these files are important for currently running programs and deleting them may result in a system crash. Usually, it won't contain more than a few KB anyway.
    - On most systems, this directory is cleared out at boot or at shutdown by the local system.
- **/usr/bin**
    - This directory contains the vast majority of binaries on your system. Executables in this directory vary widely. For instance vi, gcc, gnome-session and mozilla and are all found here.
- **/usr/share**
    - **This directory contains 'shareable', architecture-independent files (docs, icons, fonts etc).**
    - **📝 Note, however, that '/usr/share' is generally not intended to be shared by different operating systems or by different releases of the same operating system.**
    - **Any program or package that contains or requires data that doesn't need to be modified should store that data in '/usr/share' (or '/usr/local/share', if installed locally). It is recommended that a subdirectory be used in /usr/share for this purpose.”**
- **$PATH**
    - PATH is an *environmental variable* in Linux and other Unix-like operating systems that tells the *shell* which directories to search for *executable files* (i.e., ready-to-run programs) in response to commands issued by a user.

### 🤏 Basics Commands

- **Note📝:**
    
     **Linux and the UNIX system are case-sensitive**
    
    ![b2b5c449a1ca3c83842342315c6ab43e4b9c964f.png](00-assets/b2b5c449a1ca3c83842342315c6ab43e4b9c964f.png)
    
- **man Command**
    
    ***man*** command in Linux is used to display the user manual of any command that we can run on the terminal. It provides a detailed view of the command which includes `NAME, SYNOPSIS, DESCRIPTION, OPTIONS, EXIT STATUS, RETURN VALUES, ERRORS, FILES, VERSIONS, EXAMPLES, and AUTHORS`
    
    - **Every manual is divided into the following sections:**
        - Executable programs or shell commands
        - System calls (functions provided by the kernel)
        - Library calls (functions within program libraries
        - Games
        - Special files (usually found in /dev)
        - File formats and conventions eg /etc/passwd
        - Miscellaneous (including macro packages and conventions), e.g. groff(7)
        - System administration commands (usually only for root)
        - Kernel routines [Non standard]
    - **Syntax:**
        - `$**man** [OPTION]... [COMMAND NAME]...`
        - **No Option**
            - **No Option**: It displays the whole manual of the command.
            - `$**man** [COMMAND NAME]`
                
                In this example, manual pages of the command ‘*printf*‘ are simply returned.
                
                ```bash
                ┌──(kali㉿kali)-[~]
                └─$ **man** printf
                
                NAME
                       printf - format and print data
                
                SYNOPSIS
                       printf FORMAT [ARGUMENT]...
                       printf OPTION
                
                DESCRIPTION
                       Print ARGUMENT(s) according to FORMAT, or execute according to OPTION:
                
                       --help display this help and exit
                
                       --version
                              output version information and exit
                
                       FORMAT controls the output as in C printf.  Interpreted sequences are:
                
                       \"     double quote
                
                       \\     backslash
                
                       \a     alert (BEL)
                
                       \b     backspace
                
                       \c     produce no further output
                
                 Manual page printf(1) line 1 (press h for help or q to quit)
                ```
                
        - **Section-num**
            - **Section-num**: Since a manual is divided into multiple sections so this option is used to display only a specific section of a manual.
            - `$**man**` `[SECTION-NUM] [COMMAND NAME]`
                
                In this example, the manual pages of command ‘printf‘ are returned which lies in the section 3.
                
                ```bash
                ┌──(kali㉿kali)-[~]
                └─$ **man 3** printf
                
                printf(3)                                      Library Functions Manual                                     printf(3)
                
                NAME
                       printf, fprintf, dprintf, sprintf, snprintf, vprintf, vfprintf, vdprintf, vsprintf, vsnprintf - formatted out‐
                       put conversion
                
                LIBRARY
                       Standard C library (libc, -lc)
                
                SYNOPSIS
                       #include <stdio.h>
                
                       int printf(const char *restrict format, ...);
                       int fprintf(FILE *restrict stream,
                                   const char *restrict format, ...);
                       int dprintf(int fd,
                                   const char *restrict format, ...);
                       int sprintf(char *restrict str,
                                   const char *restrict format, ...);
                       int snprintf(char str[restrict .size], size_t size,
                                   const char *restrict format, ...);
                
                       int vprintf(const char *restrict format, va_list ap);
                       int vfprintf(FILE *restrict stream,
                                   const char *restrict format, va_list ap);
                       int vdprintf(int fd,
                                   const char *restrict format, va_list ap);
                       int vsprintf(char *restrict str,
                                   const char *restrict format, va_list ap);
                 Manual page printf(3) line 1 (press h for help or q to quit)
                
                ```
                
        - **-f option**
            - **Section-num**: Since a manual is divided into multiple sections so this option is used to display only a specific section of a manual.
            - `$**man**``-f [COMMAND NAME]`
                
                In this example, the manual pages of command ‘printf‘ are returned which lies in the section 3.
                
                ```bash
                ┌──(kali㉿kali)-[~]
                └─$ **man -f printf
                printf (1)           - format and print data
                printf (3)           - formatted output conversion**
                
                ```
                
        - **-a option**
            - **-a option:** This option helps us to display all the available intro manual pages in succession.
            - Display, in succession, all of the available manual pages contained within the manual.  It is possible to quit between successive displays or skip any of them.
                - `$**man**``-a [COMMAND NAME]`
                    
                    ```bash
                    ┌──(kali㉿kali)-[~]
                    └─$ man -a intro
                    --Man-- next: intro(8) [ view (return) | skip (Ctrl-D) | quit (Ctrl-C) ]
                    
                    --Man-- next: intro(32) [ view (return) | skip (Ctrl-D) | quit (Ctrl-C) ]
                    ```
                    
                    - Note:📝 in this example, you can move through the manual pages(sections) either reading(by pressing Enter) skipping(by pressing ctrl+D), or exiting(by pressing ctrl+C).
                    
        - **-k option**
            - This option searches the given command as a regular expression in all the manuals and it returns the manual pages with the section number in which it is found.
                - `$**man**``-k [COMMAND NAME]`
                    
                    ```bash
                    ┌──(kali㉿kali)-[~]
                    └─$ man -k printf
                    PA_CHAR (3const)     - define custom behavior for printf-like functions
                    PA_DOUBLE (3const)   - define custom behavior for printf-like functions
                    PA_FLAG_LONG (3const) - define custom behavior for printf-like functions
                    PA_FLAG_LONG_DOUBLE (3const) - define custom behavior for printf-like functions
                    PA_FLAG_LONG_LONG (3const) - define custom behavior for printf-like functions
                    PA_FLAG_PTR (3const) - define custom behavior for printf-like functions
                    PA_FLAG_SHORT (3const) - define custom behavior for printf-like functions
                    PA_FLOAT (3const)    - define custom behavior for printf-like functions
                    PA_INT (3const)      - define custom behavior for printf-like functions
                    PA_LAST (3const)     - define custom behavior for printf-like functions
                    PA_POINTER (3const)  - define custom behavior for printf-like functions
                    PA_STRING (3const)   - define custom behavior for printf-like functions
                    PA_WCHAR (3const)    - define custom behavior for printf-like functions
                    PA_WSTRING (3const)  - define custom behavior for printf-like functions
                    asprintf (3)         - print to allocated string
                    dprintf (3)          - formatted output conversion
                    fprintf (3)          - formatted output conversion
                    fwprintf (3)         - formatted wide-character output conversion
                    printf (1)           - format and print data
                    printf (3)           - formatted output conversion
                    printf.h (3head)     - define custom behavior for printf-like functions
                    register_printf_modifier (3) - define custom behavior for printf-like functions
                    printf_arginfo_size_function (3type) - define custom behavior for printf-like functions
                    printf_function (3type) - define custom behavior for printf-like functions
                    printf_info (3type)  - define custom behavior for printf-like functions
                    printf_va_arg_function (3type) - define custom behavior for printf-like functions
                    register_printf_specifier (3) - define custom behavior for printf-like functions
                    register_printf_type (3) - define custom behavior for printf-like functions
                    snprintf (3)         - formatted output conversion
                    sprintf (3)          - formatted output conversion
                    swprintf (3)         - formatted wide-character output conversion
                    vasprintf (3)        - print to allocated string
                    vdprintf (3)         - formatted output conversion
                    vfprintf (3)         - formatted output conversion
                    vfwprintf (3)        - formatted wide-character output conversion
                    vprintf (3)          - formatted output conversion
                    vsnprintf (3)        - formatted output conversion
                    vsprintf (3)         - formatted output conversion
                    vswprintf (3)        - formatted wide-character output conversion
                    vwprintf (3)         - formatted wide-character output conversion
                    wprintf (3)          - formatted wide-character output conversion
                    XtAsprintf (3)       - memory management functions
                    ```
                    
                    - Search the short descriptions and manual page names for the
                               keywordprintf as regular expression.  Print out any matches.
                               Equivalent toaproposprintf.
        - **-w option**
            - **-w option**: This option returns the location in which the manual page of a given command is present.
            - `$**man -w**  [COMMAND NAME]`
                
                ```bash
                ┌──(kali㉿kali)-[~]
                └─$ man -w ls
                /usr/share/man/man1/ls.1.gz
                
                ┌──(kali㉿kali)-[~]
                └─$ man --where ls
                /usr/share/man/man1/ls.1.gz
                
                ┌──(kali㉿kali)-[~]
                └─$ man --path ls
                /usr/share/man/man1/ls.1.gz
                
                ┌──(kali㉿kali)-[~]
                └─$ man --location ls
                /usr/share/man/man1/ls.1.gz
                ```
                
                - Don't actually display the manual page, but do print the
                location of the source nroff file that would be formatted.
                If the -a option is also used, then print the locations of
                all source files that match the search criteria.
                
        - **-I option**
            - **-I option**: It considers the command as case sensitive.
            - `$**man**``-I [COMMAND NAME]`
                
                ```bash
                ┌──(kali㉿kali)-[~]
                └─$ man -I printf
                PRINTF(1)                                           User Commands                                           PRINTF(1)
                
                NAME
                       printf - format and print data
                
                SYNOPSIS
                       printf FORMAT [ARGUMENT]...
                       printf OPTION
                
                DESCRIPTION
                       Print ARGUMENT(s) according to FORMAT, or execute according to OPTION:
                
                       --help display this help and exit
                
                       --version
                              output version information and exit
                
                       FORMAT controls the output as in C printf.  Interpreted sequences are:
                
                       \"     double quote
                
                       \\     backslash
                
                       \a     alert (BEL)
                
                       \b     backspace
                
                       \c     produce no further output
                
                 Manual page printf(1) line 1 (press h for help or q to quit)
                ```
                
                - `Search for manual pages case-sensitively.`
    - **Note📝:**
        
        **RTFM → Read The Fuking Manual**
        
        ![2dref5n544k51.webp](00-assets/2dref5n544k51.webp)
        
- **help Command**
    
    ***help*** The help command is **the simplest way to get information regarding a built-in shell command**. It helps you fetch information from the shell's internal documentation. It takes a text string as the command line argument and looks for the provided string in the shell's documents
    
    - **Help command itself offers three options:**
        - **d:** display only a brief description of the specified command.
        - **m:** organize the available information just as the **man command** does.
        - **s:** display the command syntax of the specified command.
    - **Syntax 📝**
        - `$**help** [OPTION]... [COMMAND NAME]...`
        - **help command**
            - Displays brief summaries of builtin commands.
            - `$help``help`
                
                ```bash
                ┌──(kali㉿kali)-[~]
                └─$ help --help 
                help: help [-dms] [pattern ...]
                    Display information about builtin commands.
                
                    Displays brief summaries of builtin commands.  If PATTERN is
                    specified, gives detailed help on all commands matching PATTERN,
                    otherwise the list of help topics is printed.
                
                    Options:
                      -d        output short description for each topic
                      -m        display usage in pseudo-manpage format
                      -s        output only a short usage synopsis for each topic matching
                                PATTERN
                
                    Arguments:
                      PATTERN   Pattern specifying a help topic
                
                    Exit Status:
                    Returns success unless PATTERN is not found or an invalid option is given.
                ```
                
                ```bash
                ┌──(kali㉿kali)-[~]
                └─$ help help
                help: help [-dms] [pattern ...]
                    Display information about builtin commands.
                
                    Displays brief summaries of builtin commands.  If PATTERN is
                    specified, gives detailed help on all commands matching PATTERN,
                    otherwise the list of help topics is printed.
                
                    Options:
                      -d        output short description for each topic
                      -m        display usage in pseudo-manpage format
                      -s        output only a short usage synopsis for each topic matching
                                PATTERN
                
                    Arguments:
                      PATTERN   Pattern specifying a help topic
                
                    Exit Status:
                    Returns success unless PATTERN is not found or an invalid option is
                ```
                
                - `We get everything we want to know about help command`
        - **help -d command**
            - Using the -d option to output short description for each topic
            - `$help -d``help`
                
                ```bash
                ┌──(kali㉿kali)-[~]
                └─$ help -d help 
                help - Display information about builtin commands.
                ```
                
                - We can see that -d flag gives a one line description for the command mentioned.
            
        - **help -m command**
            - Using the -m option to output in pseudo-manpage format
            - `$help -m``help`
                
                ```bash
                ┌──(kali㉿kali)-[~]
                └─$ help -m help 
                NAME
                    help - Display information about builtin commands.
                
                SYNOPSIS
                    help [-dms] [pattern ...]
                
                DESCRIPTION
                    Display information about builtin commands.
                
                    Displays brief summaries of builtin commands.  If PATTERN is
                    specified, gives detailed help on all commands matching PATTERN,
                    otherwise the list of help topics is printed.
                
                    Options:
                      -d        output short description for each topic
                      -m        display usage in pseudo-manpage format
                      -s        output only a short usage synopsis for each topic matching
                                PATTERN
                
                    Arguments:
                      PATTERN   Pattern specifying a help topic
                
                    Exit Status:
                    Returns success unless PATTERN is not found or an invalid option is given.
                
                SEE ALSO
                    bash(1)
                
                IMPLEMENTATION
                    GNU bash, version 5.1.16(1)-release (x86_64-pc-linux-gnu)
                    Copyright (C) 2020 Free Software Foundation, Inc.
                    License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
                ```
                
                - The -m flag gives the output in manpage like format. Man is system’s manual viewer.
        - **help -s command**
            - Using -s option to output only a short usage synopsis
            - `$help -s``help`
                
                ```bash
                ┌──(kali㉿kali)-[~]
                └─$ help -s help 
                help: help [-dms] [pattern ...]
                ```
                
                - -s flag displays the command syntax of the specified command.
            
- **apropos Command**
    
    **apropos** Linux/Unix comes with a huge number of commands and thus it becomes quite difficult sometimes to remember each and every command.
    
     **apropos** command becomes useful in such cases. *apropos* command helps the user when they don’t remember the exact command but know a few keywords related to the command that define its uses or functionality.
    
     It searches the **Linux man page** with the help of the keyword provided by the user to find the command and its functions.
    
    - `apropos [OPTION..] INPUT`
    - **Syntax 📝**
        - $`**apropos** [OPTION..] INPUT` ``
        - `**apropos**`
            - Suppose you don’t know how to compress a file then you could type the following command in the terminal and it will show all the related commands and their short descriptions or functionality.
            - `$**apropos** input`
                
                Suppose you don’t know how to compress a file then you could type the following command in the terminal and it will show all the related commands and its short description or functionality.
                
                ```bash
                ┌──(kali㉿kali)-[~]
                └─$ apropos compress
                fsck.cramfs (8)      - fsck compressed ROM file system
                gunzip (1)           - compress or expand files
                gzexe (1)            - compress executable files in place
                gzip (1)             - compress or expand files
                logrotate (8)        - rotates, compresses, and mails system logs
                logrotate.conf (5)   - rotates, compresses, and mails system logs
                lzcat (1)            - Compress or decompress .xz and .lzma files
                lzcmp (1)            - compare compressed files
                lzdiff (1)           - compare compressed files
                lzegrep (1)          - search compressed files for a regular expression
                lzfgrep (1)          - search compressed files for a regular expression
                lzgrep (1)           - search compressed files for a regular expression
                lzless (1)           - view xz or lzma compressed (text) files
                lzma (1)             - Compress or decompress .xz and .lzma files
                lzmore (1)           - view xz or lzma compressed (text) files
                mkfs.cramfs (8)      - make compressed ROM file system
                pbget (1)            - compress and encode arbitrary files to pastebin.com
                pbput (1)            - compress and encode arbitrary files to pastebin.com
                pbputs (1)           - compress and encode arbitrary files to pastebin.com
                uncompress (1)       - compress or expand files
                unlzma (1)           - Compress or decompress .xz and .lzma files
                unsquashfs (1)       - tool to uncompress squashfs filesystems
                unxz (1)             - Compress or decompress .xz and .lzma files
                xz (1)               - Compress or decompress .xz and .lzma files
                xzcat (1)            - Compress or decompress .xz and .lzma files
                xzcmp (1)            - compare compressed files
                xzdiff (1)           - compare compressed files
                xzegrep (1)          - search compressed files for a regular expression
                xzfgrep (1)          - search compressed files for a regular expression
                xzgrep (1)           - search compressed files for a regular expression
                xzless (1)           - view xz or lzma compressed (text) files
                xzmore (1)           - view xz or lzma compressed (text) files
                zcat (1)             - compress or expand files
                zcmp (1)             - compare compressed files
                zdiff (1)            - compare compressed files
                zegrep (1)           - search possibly compressed files for a regular expression
                zfgrep (1)           - search possibly compressed files for a regular expression
                zgrep (1)            - search possibly compressed files for a regular expression
                zless (1)            - file perusal filter for crt viewing of compressed text
                zmore (1)            - file perusal filter for crt viewing of compressed text
                znew (1)             - recompress .Z files to .gz files
                ```
                
                - After executing the above command you will observe a bunch of commands listed on the terminal that deal with not only how to compress a file but also how to expand a compressed file, search a compressed file, comparing a compressed file, etc.
            - **Note📝:**
                
                ***apropos*** also support multiple keywords if given as an argument i.e. we can also provide more than one keyword for a better search. 
                
                Thus, if two keywords are provided the **apropos** command will display all the command’s list which contains either the first keyword in its man page description or the second keyword.
                
                ```bash
                ┌──(kali㉿kali)-[~]
                └─$ apropos email address
                addr2line (1)        - convert addresses into file names and line numbers
                address_families (7) - socket address families (domains)
                bridge (8)           - show / manipulate bridge addresses and devices
                byobu-reconnect-sockets (1) - Sourcable script that updates GPG_AGENT_INFO and DBUS_SESSION_BUS_ADDRESS in the enviro...
                devlink-region (8)   - devlink address region access
                dladdr (3)           - translate address to symbolic information
                dladdr1 (3)          - translate address to symbolic information
                dlsym (3)            - obtain address of a symbol in a shared object or executable
                dlvsym (3)           - obtain address of a symbol in a shared object or executable
                ether_aton (3)       - Ethernet address manipulation routines
                ether_aton_r (3)     - Ethernet address manipulation routines
                ether_hostton (3)    - Ethernet address manipulation routines
                ether_line (3)       - Ethernet address manipulation routines
                ether_ntoa (3)       - Ethernet address manipulation routines
                ether_ntoa_r (3)     - Ethernet address manipulation routines
                ether_ntohost (3)    - Ethernet address manipulation routines
                ethers (5)           - Ethernet address to IP number database
                freeaddrinfo (3)     - network address and service translation
                freehostent (3)      - get network hostnames and addresses
                freeifaddrs (3)      - get interface addresses
                gai_cancel (3)       - asynchronous network address and service translation
                gai_error (3)        - asynchronous network address and service translation
                gai_strerror (3)     - network address and service translation
                gai_suspend (3)      - asynchronous network address and service translation
                get_myaddress (3)    - library routines for remote procedure calls
                rpc_soc (3t)         - "library routines for remote procedure calls"
                getaddrinfo (3)      - network address and service translation
                getaddrinfo_a (3)    - asynchronous network address and service translation
                getifaddrs (3)       - get interface addresses
                getipnodebyaddr (3)  - get network hostnames and addresses
                getipnodebyname (3)  - get network hostnames and addresses
                getnameinfo (3)      - address-to-name translation in protocol-independent manner
                git-check-mailmap (1) - Show canonical names and email addresses of contacts
                gitmailmap (5)       - Map author/committer names and/or E-Mail addresses
                gpgparsemail (1)     - Parse a mail message into an annotated format
                inet (3)             - Internet address manipulation routines
                inet_addr (3)        - Internet address manipulation routines
                inet_aton (3)        - Internet address manipulation routines
                inet_lnaof (3)       - Internet address manipulation routines
                inet_makeaddr (3)    - Internet address manipulation routines
                inet_netof (3)       - Internet address manipulation routines
                inet_network (3)     - Internet address manipulation routines
                inet_ntoa (3)        - Internet address manipulation routines
                inet_ntop (3)        - convert IPv4 and IPv6 addresses from binary to text form
                inet_pton (3)        - convert IPv4 and IPv6 addresses from text to binary form
                ip-address (8)       - protocol address management
                ip-addrlabel (8)     - protocol address label management
                ip-maddress (8)      - multicast addresses management
                mailaddr (7)         - mail addressing description
                mremap (2)           - remap a virtual memory address
                nameif (8)           - name network interfaces based on MAC addresses
                process_vm_readv (2) - transfer data between process address spaces
                process_vm_writev (2) - transfer data between process address spaces
                pthread_attr_getstackaddr (3) - set/get stack address attribute in thread attributes object
                pthread_attr_setstackaddr (3) - set/get stack address attribute in thread attributes object
                resolvconf (1)       - Resolve domain names, IPV4 and IPv6 addresses, DNS resource records, and services; introspect ...
                resolvectl (1)       - Resolve domain names, IPV4 and IPv6 addresses, DNS resource records, and services; introspect ...
                set_tid_address (2)  - set pointer to thread ID
                subpage_prot (2)     - define a subpage protection for an address range
                tc-nat (8)           - stateless native address translation action
                vsock (7)            - Linux VSOCK address family
                x86_64-linux-gnu-addr2line (1) - convert addresses into file names and line numbers
                ```
                
        - **-d Option**
            - `$**apropos** -d email`
                
                -d, --debug
                Print debugging information.
                
                ```bash
                ┌──(kali㉿kali)-[~]
                └─$ apropos -d email 
                From the config file /etc/manpath.config:
                  Mandatory mandir `/usr/man'.
                  Mandatory mandir `/usr/share/man'.
                  Mandatory mandir `/usr/local/share/man'.
                  Path `/bin' mapped to mandir `/usr/share/man'.
                  Path `/usr/bin' mapped to mandir `/usr/share/man'.
                  Path `/sbin' mapped to mandir `/usr/share/man'.
                  Path `/usr/sbin' mapped to mandir `/usr/share/man'.
                  Path `/usr/local/bin' mapped to mandir `/usr/local/man'.
                  Path `/usr/local/bin' mapped to mandir `/usr/local/share/man'.
                  Path `/usr/local/sbin' mapped to mandir `/usr/local/man'.
                  Path `/usr/local/sbin' mapped to mandir `/usr/local/share/man'.
                  Path `/usr/X11R6/bin' mapped to mandir `/usr/X11R6/man'.
                  Path `/usr/bin/X11' mapped to mandir `/usr/X11R6/man'.
                  Path `/usr/games' mapped to mandir `/usr/share/man'.
                  Path `/opt/bin' mapped to mandir `/opt/man'.
                  Path `/opt/sbin' mapped to mandir `/opt/man'.
                  Global mandir `/usr/man', catdir `/var/cache/man/fsstnd'.
                  Global mandir `/usr/share/man', catdir `/var/cache/man'.
                  Global mandir `/usr/local/man', catdir `/var/cache/man/oldlocal'.
                  Global mandir `/usr/local/share/man', catdir `/var/cache/man/local'.
                  Global mandir `/usr/X11R6/man', catdir `/var/cache/man/X11R6'.
                  Global mandir `/opt/man', catdir `/var/cache/man/opt'.
                  Global mandir `/snap/man', catdir `/var/cache/man/snap'.
                  Added sections: `1', `n', `l', `8', `3', `0', `2', `3posix', `3pm', `3perl', `3am', `5', `4', `9', `6', `7'.
                ```
                
                - This option is used to emit debugging messages. When this option is used then terminal returns man directories, global path, path directory, warnings, etc. of each command which is related to the search keyword.
        - **-v Option**
            - `$**apropos** -v email`
                
                -v, --verbose
                Print verbose warning messages.
                
                ```bash
                ┌──(kali㉿kali)-[~]
                └─$ apropos -v email 
                git-check-mailmap (1) - Show canonical names and email addresses of contacts
                gpgparsemail (1)     - Parse a mail message into an annotated format
                ```
                
                - -**v**: This option is used to print verbose warning messages.
        - **-e Option**
            - `$**apropos** -e ls`
                
                e, --exact
                Each keyword will be exactly matched against the page names and the descriptions.
                
                ```bash
                ┌──(kali㉿kali)-[~]
                └─$ apropos -e ls 
                dircolors (1)        - color setup for ls
                git-mktree (1)       - Build a tree-object from ls-tree formatted text
                ls (1)               - list directory contents
                ```
                
                - **-e**, **–exact**: This option is used to search each keyword for exact match. If no option is used, the apropos command returns list of all the command whose description in the man page description matches with the keyword or which are somehow related to the keyword given in the argument.
                - However, when the *-e* option is used, the apropos only returns the command whose description exactly matches with the keyword.
        - **For more Options…….**
            
            
            ![Mao_RTFM_vectorize_by_cmenghi.png](00-assets/Mao_RTFM_vectorize_by_cmenghi.png)
            
            ![BabyRunGIF.gif](00-assets/BabyRunGIF.gif)
            
- **ls Command**
    
    **ls** is a Linux shell command that lists directory contents of files and directories.  It provides valuable information about files, directories, and their attributes.
    
    - `ls [option] [file/directory]`
    - **Syntax 📝**
        - `ls [option] [file/directory]`
        
        | Options | Description |
        | --- | --- |
        | -l | known as a long format that displays detailed information about files and directories. |
        | -a | Represent all files Include hidden files and directories in the listing. |
        | -t | Sort files and directories by their last modification time, displaying the most recently modified ones first. |
        | -r | known as reverse order which is used to reverse the default order of listing. |
        | -S | Sort files and directories by their sizes, listing the largest ones first. |
        | -R | List files and directories recursively, including subdirectories. |
        | -i | known as inode which displays the index number (inode) of each file and directory. |
        | -g | known as group which displays the group ownership of files and directories instead of the owner. |
        | -h | Print file sizes in human-readable format (e.g., 1K, 234M, 2G). |
        | -d | List directories themselves, rather than their contents. |
- **mv Command**
    
    **`mv`** is a [Unix](https://en.wikipedia.org/wiki/Unix) command that [moves](https://en.wikipedia.org/wiki/Computer_file#Operations) one or more [files](https://en.wikipedia.org/wiki/Computer_file) or [directories](https://en.wikipedia.org/wiki/Directory_(computing)) from one place to another. If both filenames are on the same filesystem, this results in a simple file rename; otherwise, the file content is copied to the new location and the old file is removed
    
    - **Syntax 📝**
        - **Renaming a file in Linux**
            - **`mv [source_file_name(s)] [Destination_file_name]`**
            
            Enter your **source file name** in place of **[source_file_name(s)]** and your **destination file name** in place of **[Destination_file_name].**
            
            ```bash
            ┌──(kali㉿kali)-[~]
            └─$ ls
            **fileA.txt**  fileB.txt  fileC.txt  fileD.txt  fileE.txt  fileF.txt
            ┌──(kali㉿kali)-[~]
            └─$ mv **fileA.txt filea.txt**
            ┌──(kali㉿kali)-[~]
            └─$ ls
            fileB.txt  fileC.txt  fileD.txt  fileE.txt  fileF.txt  **filea.txt**
            ```
            
            - **`mv [source_file_name(s)] [Destination_file_name]`**
        - **Moving a file in Linux**
            
            **`mv [source_file_name(s)] [Destination_path]`**
            
            Enter your **source file name** in place of **[source_file_name(s)]** and your **destination path** in place of **[Destination_path].**
            
            ```bash
            ┌──(kali㉿kali)-[~]
            └─$ ls -l
            total 0
            drwxr-xr-x 1 kali kali 4096 Oct  8 09:04 **Ibrahim**
            ┌──(kali㉿kali)-[~]
            └─$ mv **Ibrahim** /tmp/folder/
            ┌──(kali㉿kali)-[~]
            └─$ ls -l /tmp/folder/
            total 0
            drwxr-xr-x 1 kali kali 4096 Oct  8 09:06 Ibrahim
            ```
            
- **pwd Command**
    
    **pwd** stands for **Print Working Directory**. It prints the path of the working directory, starting from the root. pwd is shell bult-in command(pwd) or an actual binary(/bin/pwd).
    
    - **Syntax 📝**
        
        `pwd [OPTIONS]`
        
        This command doesn’t have any arguments or options, but it can accept flags for specific behavior.
        
        - **Flags For Specific behavior in `pwd` command in Linux.**
            - The “-L” flag resolves symbolic links and prints the path of the target directory.
            - The default behavior of the shell built-in “pwd” is equivalent to using “pwd -L”.
            - Mention the “-P” flag, which displays the actual path without resolving symbolic links.
            - The default behavior of the binary “/bin/pwd” is the same as using “pwd -P”
- **mkdir Command**
    
    **mkdir** command in Linux allows the user to create directories (also referred to as folders in some operating systems). This command can create multiple directories at once as well as set the permissions for the directories. It is important to note that the user executing this command must have enough permission to create a directory in the parent directory, or he/she may receive a ‘permission denied’ error.
    
    - **Syntax 📝**
        
        `mkdir [options...] [directories ...]`
        
- **rm Command**
    
    **rm** stands for **remove** here. rm command is used to remove objects such as files, directories, symbolic links and so on from the file system like UNIX. To be more precise, rm removes references to objects from the filesystem, where those objects might have had multiple references (for example, a file with two different names). **By default, it does not remove directories.** This command normally works silently and you should be very careful while running **rm** command because once you delete the files then you are not able to recover the contents of files and directories.
    
    - **Syntax 📝**
        
        **`rm [OPTION]... FILE...`**
        
- **cp Command**
    
    **cp** stands for a **copy**. This command is used to copy files or groups of files or **[directories](https://www.geeksforgeeks.org/structures-of-directory-in-operating-system/)**. It creates an exact image of a file on a disk with a different file name. *cp* command requires at least two filenames in its arguments.
    
    - **Syntax 📝**
        
        **`rm [OPTION]... FILE...`**
        
        **cp** [OPTION] Source Destination
        
        **cp** [OPTION] Source Directory
        
        **cp** [OPTION] Source-1 Source-2 Source-3 Source-n Directory
        
        The first and second syntax is used to copy the Source file to the Destination file or Directory.
        The third syntax is used to copy multiple Sources(files) to the Directory.
        
- **sudo command**
    
    **sudo** (**S**uper **U**ser **DO**) command in Linux is generally used as a prefix for some commands that only superusers are allowed to run. If you prefix any command with “sudo”, it will run that command with elevated privileges or in other words allow a user with proper permissions to execute a command as another user, such as the superuser. This is the equivalent of the “run as administrator” option in Windows. The option of sudo lets us have multiple administrators.
    
    - **syntax for the `sudo` command:**
        
        sudo-V | -h | -l | -v | -k | -K | -s | [ -H ] [-P ] [-S ] [ -b ] |[ -p prompt ] [ -c class|- ] [ -a auth_type ] [-r role ] [-t type ][ -u username|#uid ]command
        
        **Options Available in the `sudo` command**
        
        | Options | Description | Syntax |
        | --- | --- | --- |
        | -V | The -V (version) option causes sudo to print the version number and exit. If the invoking user is already root, the -V option will print out a list of the defaults sudo was compiled with. | sudo -V |
        | -l | The -l (list) option will print out the commands allowed (and forbidden) the user on the current host. | sudo -l |
        | -h or –help | The -h (help) option causes sudo to print a usage message and exit. | sudo -h |
        | -v | If, given the -v (validate) option, sudo will update the user’s timestamp, prompting for the user’s password if necessary. This extends the sudo timeout for another 5 minutes (or as given in sudoers) but does not run a command. This does not give any output. | sudo -v |
        | -k | The -k (kill) option to sudo invalidates the user’s timestamp. So, the next time sudo is run a password will be required. This option does not require a password and was added to allow a user to revoke sudo permissions from a logout file. | sudo -k |
        | -K | Similar to the -k option, the -K (sure kill) option is used to remove the user’s timestamp entirely. Likewise, this option does not require a password. | sudo -K |
        | -b | The -b (background) option tells sudo to run the given command in the background. Note that if you use the -b option you cannot use shell https://www.geeksforgeeks.org/process-control-commands-unixlinux/ to manipulate the process. | sudo -b [command]
        (replace “command” with the command you want run in the background) |
        | -p | the sudo -p prompt command allows you to customize the password prompt that sudo displays when it requests the user’s password. By default, sudo will display a generic password prompt that looks like | sudo -p "Enter your password" [command]
        (replace “command” with the command you want run in the background) |
        | -n | The -n option allows sudo to execute a command without prompting for a password. This option is useful when running sudo commands as background jobs or in a shell script. The -n option stands for non-interactive. | sudo -n [command]
        (replace “command” with the command you want run in the background) |
        | -u | The -u option causes sudo to run the specified command as a user other than root. To specify a UID instead of a username, use #uid. | sudo -u [user] [command]
        (replace “command” with the command you want run in the background) |
        | -s | The -s option runs the shell specified by the SHELL environment variable if it is set or the shell as specified in the file passwd. | sudo -s [command]
        (replace “command” with the command you want run in the background) |
        | -H | The -H option sets the HOME environment variable to the home directory of the target user (root by default) as specified in passwd. By default, sudo does not modify HOME. | sudo -H [command]
        (replace “command” with the command you want run in the background) |
        | -S | The -S option causes sudo to read the password from standard input instead of the terminal device. | sudo -S [command]
        (replace “command” with the command you want run in the background) |
        | -a | The -a option causes sudo to use the specified authentication type when validating the user, as allowed by /etc/login.conf. The system administrator may specify a list of sudo-specific authentication methods by adding an “auth-sudo” entry in /etc/login.conf. | sudo -a [auth-type] [command]
        (replace “command” with the command you want run in the background) |
        | — | The — flag indicates that sudo should stop processing command line arguments. It is most useful in conjunction with the -s flag. | sudo -- [command]
        (replace “command” with the command you want run in the background) |
        
    - **Accomplish previous commands with sudo**
        
        Commands that have been executed previously are stored in the Linux command line. By pressing the up arrow, you can access these records. Use the following command to repeat the last command with enhanced privileges:
        
        `sudo !!`
        
    - **Environment Variable with sudo**
        
        
        | Tag | Description |
        | --- | --- |
        | EDITOR  | Default editor to use in -e (sudoedit) mode if VISUAL is not set  |
        | HOME  | In -s or -H mode (or if sudo was configured with the –enable-shell-sets-home option), set to homedir of the target user 
         |
        | PATH  | Set to a sane value if the secure_path sudoers option is set. 
         |
        | SHELL  | Used to determine shell to run with -s option  |
        | SUDO_PROMPT  | Used as the default password prompt  |
        | SUDO_COMMAND  | Set to the command run by sudo  |
        | SUDO_USER  | Set to the login of the user who invoked sudo  |
        | SUDO_UID  | Set to the uid of the user who invoked sudo  |
        | SUDO_GID  | Set to the gid of the user who invoked sudo  |
        | SUDO_PS1  | If set, PS1 will be set to its value  |
        | USER  | Set to the target user (root unless the -u option is specified) 
         |
        | VISUAL  | Default editor to use in -e (sudoedit) mode  |
    
- **adduser command or useradd**
    
    **adduser** command in Linux is used to add a new user to your current Linux machine. This command allows you to modify the configurations of the user which is to be created. It is similar to the **useradd** command in Linux. The adduser command is much interactive as compared to useradd command.
    
    - **Syntax:**
        
        `adduser username`
        
- **su command**
    
    The standard function of `su` command , if summoned without any options, is to drive an interactive shell as root:
    
    - Syntax:
        
        `su [OPTIONS] [USER [ARGUMENT...]]`
        

### 💬 Text Editing

- **echo command**
    
    The **echo** command in Linux is a built-in command that allows users to display lines of text or strings that are passed as arguments. It is commonly used in shell scripts and batch files to output status text to the screen or a file.
    
    - **Syntax:**
        
        `echo [option] [string]`
        
- **nano command**
    
    **nano** is a user-friendly, simple and WYSIWYG(What You See Is What You Get) text editor, which improves the features and user-friendliness of UW Pico text editor. Unlike vim editor or any other command-line editor, it doesn’t have any mode. It has an easy GUI(Graphical User Interface) which allows users to interact directly with the text in spite of switching between the modes as in vim editor.
    
    - **Syntax:**
        
        `nano filename`
        
- **cat command**
    
    ![4nxl3m.jpg](00-assets/4nxl3m.jpg)
    
    Cat(concatenate) command is very frequently used in Linux. It reads data from the file and gives its content as output. It helps us to create, view, and concatenate files. So let us see some frequently used cat commands.
    
    ![systemd_cat.jpg](00-assets/systemd_cat.jpg)
    
    - **Syntax:**
        
        `cat file_name`
        
        ![1XHi4pf.png](00-assets/1XHi4pf.png)
        
- **which command**
    
    **which** command in Linux is a command which is used to locate the executable file associated with the given command by searching it in the path environment variable. It has 3 return statuses as follows:
    
    - **0** : If all specified commands are found and executable.
    - **1** : If one or more specified commands is nonexistent or not executable.
    - **2** : If an invalid option is specified.
    - **Syntax:**
        
        `which [filename1] [filename2] ...`
        
- **locate command**
    
    ***locate*** command in Linux is used to find the files by name. There are two most widely used file-searching utilities accessible to users called to find and *locate*. The *locate* utility works better and faster than the *find* command counterpart because instead of searching the file system when a file search is initiated, it would look through a database. This database contains bits and parts of files and their corresponding paths on your system. By default, the locate command does not check whether the files found in the database still exist and it never reports files created after the most recent update of the relevant database.
    
    - **Syntax:**
        
        `locate [OPTION]... PATTERN..`
        
    - **Options Available in `locate` command in Linux**
    
    | OPTIONS | DESCRIPTION |
    | --- | --- |
    | -b, –basename | Match only the base name against the specified patterns, which is the opposite of –whole name. |
    | -c, –count | Instead of writing file names on standard output, write the number of matching entries only. |
    | -d, –database DBPAT | Replace the default database with DBPATH. DBPATH is a : (colon) separated list of database file names. If more than one –database option is specified, the resulting path is a concatenation of the separate paths. An empty database file name is replaced by the default database. A database file name – refers to the standard input. Note that a database can be read from the standard input only once. |
    | -e, –existing | Print only entries that refer to files existing at the time locate is run. |
    | -L, –follow | When checking whether files exist (if the –existing option is specified), follow trailing symbolic links. This causes bro ken symbolic links to be omitted from the output. This option is the default behavior. The opposite can be specified using –nofollow. |
    | -h, –help | Write a summary of the available options to standard output and exit successfully. |
    | -i, –ignore-case | Ignore case distinctions when matching patterns. |
    | -l, –limit, -n LIMIT | Exit successfully after finding LIMIT entries. If the –count option is specified, the resulting count is also limited to LIMIT. |
    | -m, –mmap | Ignored, but included for compatibility with BSD and GNU locate. |
    | -P, –nofollow, -H | When checking whether files exist (if the –existing option is specified), do not follow trailing symbolic links. This causes broken symbolic links to be reported like other files. This option is the opposite of –follow. |
    | -0, –null | Separate the entries on output using the ASCII NULL character instead of writing each entry on a separate line. This option is designed for interoperability with the –null option of GNU xargs. |
    | -S, –statistics | Write statistics about each read database to standard output instead of searching for files and exit successfully. |
    | q, –quiet | Write no messages about errors encountered while reading and processing databases. |
    | -r, –regexp REGEXP | Search for a basic regexp REGEXP. No PATTERNs are allowed if this option is used, but this option can be specified multiple times. |
    | –regex | Interpret all PATTERNs as extended regexps. |
    | -s, –stdio | Ignored, for compatibility with BSD and GNU locate. |
    | -V, –version | Write information about the version and license of locate on standard output and exit successfully. |
    | -w, –wholename | Match only the whole path name against the specified patterns. This option is the default behavior. The opposite can be specified using –basename. |
- **find command**
    
    The **find** command in UNIX is a command line utility for walking a file hierarchy. It can be used to find files and directories and perform subsequent operations on them. It supports searching by file, folder, name, creation date, modification date, owner, and permissions. By using the ‘-exec’ other UNIX commands can be executed on files or folders found.
    
    - **Syntax:**
        
        `$ find [where to start searching from]`
        
        `[expression determines what to find] [-options] [what to find]`
        
    - **exec CMD:** The file being searched which meets the above criteria and returns 0 for as its exit status for successful command execution.
    - **ok CMD :** It works same as -exec except the user is prompted first.
    - **inum N :** Search for files with inode number ‘N’.
    - **links N :** Search for files with ‘N’ links.
    - **name demo :** Search for files that are specified by ‘demo’.
    - **newer file :** Search for files that were modified/created after ‘file’.
    - **perm octal :** Search for the file if permission is ‘octal’.
    - **print :** Display the path name of the files found by using the rest of the criteria.
    - **empty :** Search for empty files and directories.
    - **size +N/-N :** Search for files of ‘N’ blocks; ‘N’ followed by ‘c’can be used to measure the size in characters; ‘+N’ means size > ‘N’ blocks and ‘-N’ means size < ‘N’ blocks.
    - **user name :** Search for files owned by username or ID ‘name’.
    - **\(expr \) :** True if ‘expr’ is true; used for grouping criteria combined with OR or AND.
    - **! expr :** True if ‘expr’ is false.
- **updatedb command**
    
    The `updatedb` command is typically run as a daily cron job to ensure that the database files are up to date. However, you can also run it manually when you need to update the database files immediately.
    
    - **Syntax:**
        
        `updatedb [OPTION]...`
        
- **Task📝**
    - [x]  **Add User with root permissions**
    - **solution**
        
        **Add The User**
        
        1. **Create a username for your new user, in my example my new user is ibrahim:**
            
            ```bash
            ┌──(kali㉿kali)-[~]
            └─$ sudo adduser ibrahim
            		Adding user `ibrahim' ...
            		Adding new group `ibrahim' (1001) ...
            		Adding new user `ibrahim' (1001) with group `ibrahim' ...
            		Creating home directory `/home/ibrahim' ...
            		Copying files from `/etc/skel' ...
            		New password:
            		Retype new password:
            		passwd: password updated successfully
            		Changing the user information for ibrahim
            		Enter the new value, or press ENTER for the default
            		        Full Name []: Ibrahim Sallam
            		        Room Number []:
            		        Work Phone []:
            		        Home Phone []:
            		        Other []:
            ```
            
        2. **Grant Root Privileges:**
            
            ```bash
            ┌──(kali㉿kali)-[~]
            └─$ sudo usermod -aG sudo ibrahim
            ```
            
        3. **Verify New User**
            
            ```bash
            ┌──(kali㉿kali)-[~]
            └─$ su - ibrahim
            		grep '^sudo' /etc/group
            		sudo:x:27:kardl,ibrahim
            ```
            

### 🌐Network IP

- **Network commands**
    - **ifconfig**
        
        **ifconfig** displays the current configuration for a network interface when no optional parameters are supplied
        
        ```bash
        ┌──(kali㉿kali)-[~]
        └─$ ifconfig
        		eth0: flags=4443<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1025
                inet 192.168.0.0  netmask 255.255.255.0  broadcast 192.168.0.0
                ether 6c:f0:49:25:d7:0a  (Ethernet)
                RX packets 0  bytes 0 (0.0 B)
                RX errors 0  dropped 0  overruns 0  frame 0
                TX packets 0  bytes 0 (0.0 B)
                TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
        
        		eth1: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
                inet 192.168.0.0  netmask 255.255.255.0  broadcast 192.168.0.0
        ```
        
    - **ip a**
        
        **Ip** command in Linux is present in the net-tools which are used for performing several network administration tasks. IP stands for Internet Protocol. This command is used to show or manipulate routing, devices, and tunnels
        
        ```bash
        ┌──(kali㉿kali)-[~]
        └─$ ip
        		15: eth0: <BROADCAST,MULTICAST,UP> mtu 1500 group default qlen 1
            link/ether 6c:f0:49:25:d7:0a
            inet 192.168.0.0/24 brd 192.168.0.0 scope global dynamic
               valid_lft 758245sec preferred_lft 758245sec 
        ```
        
    - **ip add**
        
        To add an IP address to an existing link/interface, use the addr add command. The format for the command is **ip addr add ADDRESS/NETMASK dev LINK_ID**
        
        ```bash
        ┌──(kali㉿kali)-[~]
        └─$ ip a add (ip_address) dev (interface)
        ```
        
    
- **reference**
    
    [rh_ip_command_cheatsheet_1214_jcs_print.pdf](00-assets/rh_ip_command_cheatsheet_1214_jcs_print.pdf)
    

### 🕸️ **Managing Kali services**

Having certain services start automatically can be useful in Kali Linux. For example, let's say I want to be able to SSH (covered in the *Configuring and using SSH* recipe) to my Kali Linux distribution. By default, the SSH server does not start in Kali, so I would need to log in to the virtual machine, open a Terminal, and run the command to start the service.

- **SSH Service**
    
    ```bash
    	┌──(kali㉿kali)-[~]
    	└─$ sudo apt-get install openssh-server
    			Reading package lists... Done
    			Building dependency tree... Done
    			Reading state information... Done
    			The following additional packages will be installed:
    			  libwrap0 ncurses-term openssh-client openssh-sftp-server ssh-import-id
    			Suggested packages:
    			  keychain libpam-ssh monkeysphere ssh-askpass molly-guard
    			The following NEW packages will be installed:
    			  libwrap0 ncurses-term openssh-server openssh-sftp-server ssh-import-id
    			The following packages will be upgraded:
    			  openssh-client
    			1 upgraded, 5 newly installed, 0 to remove and 28 not upgraded.
    			Need to get 1703 kB of archives.
    			After this operation, 6157 kB of additional disk space will be used.
    			Do you want to continue? [Y/n]	Y
    
    	┌──(kali㉿kali)-[~]
    	└─$ service ssh status 
    			ssh.service OpenBSD Secure Shell server
    			Loaded: loaded (/lib/systemd/system/ssh.service; disabled; vendor preset: disabled)
    			Active: active (running) since Sun 2019-10-20 13:06:43 CEST; 8min ago
    			Docs: man: sshd (8)
    			man: sshd_config(5)
    			Process: 3570 ExecStartPre=/usr/sbin/sshd -t (code=exited, status=0/SUCCESS)
    			Main PID: 3583 (sshd)
    			Tasks: 1 (limit: 4915)
    			Memory: 3.5M
    			CGroup: /system.slice/ssh.service
    			L3583 /usr/sbin/sshd -D
    			Okt 20 13:10:30 kali sshd[11192]: Failed password for root from ::1 port 55520 ssh2
    			Okt 20 13:10:40 kali sshd[11192]: Failed password for root from ::1 port 55520 ssh2 Okt 20 13:10:57 kali sshd[11192]: Failed password for root from ::1 port 55520 ssh2
    			Okt 20 13:10:57 kali sshd[11192]: Connection closed by authenticating user root ::1 port 555
    			Okt 20 13:10:57 kali sshd[11192]: PAM 2 more authentication failures; logname= uid=0 euid=0
    			Okt 20 13:14:09 kali sshd[18949]: pam_unix(sshd: auth): authentication failure; logname= uid=
    			Okt 20 13:14:12 kali sshd[18949]: Failed password for root from ::1 port 55522 ssh2
    			Okt 20 13:14:23 kali sshd[18949]: Failed password for root from ::1 port 55522 ssh2
    			Okt 20 13:14:59 kali sshd[18949]: Connection closed by authenticating user root ::1 port 555 Okt 20 13:14:59 kali sshd[18949]: PAM 1 more authentication failure; logname= uid=0 euid=0 t
    	┌──(kali㉿kali)-[~]
    	└─$ service ssh start
    ```
    
- **HTTP Service**
    
    [Kali http server setup](https://linuxconfig.org/kali-http-server-setup)
    

### 🐧 Important Commands

- **sudo service [service] [command]**
    
    The `sudo service [service] [command]` command is used to control System V init services in Linux. It is a powerful tool that can be used to start, stop, restart, and reload services.
    
    To use the `sudo service` command, you must be logged in as a user with sudo privileges. This means that you can run commands as the root user.
    
    ```bash
    ┌──(kali㉿kali)-[~]
    └─$ sudo service apache2 restart
    ```
    
- **sudo systemctl [service] [command]**
    
    The `sudo systemctl [service] [command]` command is used to control Systemd services in Linux. Systemd is a newer init system that is replacing SysV init on most Linux distributions.
    
    To use the `sudo systemctl` command, you must be logged in as a user with sudo privileges. This means that you can run commands as the root user.
    
    ```bash
    ┌──(kali㉿kali)-[~]
    └─$ sudo service apache2 restart
    ```
    
- **sudo systemctl list-unit-files**
    
    The `sudo systemctl list-unit-files` command lists all of the unit files installed on the system, in combination with their enablement state. Unit files are files that describe system services, sockets, timers, device nodes, and other entities that systemd manages.
    
    To use the `sudo systemctl list-unit-files` command, you must be logged in as a user with sudo privileges. This means that you can run commands as the root user.
    
    ```bash
    ┌──(kali㉿kali)-[~]
    └─$ sudo systemctl list-unit-files --type service
    ```
    
- **passwd**
    
    The `passwd` command is used to change the password of the current user or another user on the system. If no user is specified, the password of the current user is changed.
    
    ```bash
    ┌──(kali㉿kali)-[~]
    └─$ sudo passwd <username>
    ```
    

### 🔎 Searching, installing, and removing tools

- **sudo apt-get update**
    
    `sudo apt-get update` fetches the latest version of the package list from your distro's software repository and any third-party repositories you may have configured. In other words, it'll figure out what the latest version of each package and dependency is, but will not actually download or install any of those updates.
    
    ```bash
    ┌──(kali㉿kali)-[~]
    └─$ sudo apt-get update
    ```
    
- **sudo apt-get upgrade**
    
    The `sudo apt-get upgrade` command downloads and installs the updates for each outdated package and dependency on your system. But just running `sudo apt-get upgrade` will not automatically upgrade the outdated packages – you'll still have a chance to review the changes and confirm that you want to perform the upgrades.
    
    ```bash
    ┌──(kali㉿kali)-[~]
    └─$ sudo apt-get update
    ```
    
- **sudo apt-get upgrade**
    
    The `sudo apt-get upgrade` command downloads and installs the updates for each outdated package and dependency on your system. But just running `sudo apt-get upgrade` will not automatically upgrade the outdated packages – you'll still have a chance to review the changes and confirm that you want to perform the upgrades.
    
    ```bash
    ┌──(kali㉿kali)-[~]
    └─$ sudo apt-get update
    ```
    
- Use the `apt-cache show` command to view information about a package, such as its version, description, and dependencies.
- Use the `apt-cache search` command to search for packages by name or keyword.
- Use the `apt-get install` command to install a package.
- Use the `apt-get remove` command to remove a package.
- Use the `apt-get update` command to update the list of available packages.
- Use the `apt-get upgrade` command to upgrade all installed packages to the latest version.
- Use the `apt-get dist-upgrade` command to upgrade all installed packages, including removing and installing packages as needed.
- Use the `apt-get autoremove` command to remove packages that are no longer needed.
- Use the `apt-get clean` command to remove downloaded package files.
- Use the `apt-get autoclean` command to remove downloaded package files that are no longer needed.

**Install a package:**

 `dpkg -i [/path/to/vim_7.3.429-2ubuntu2_amd64.deb]`

or alternatively, use the `--install` flag

 `dpkg --install [/path/to/vim_7.3.429-2ubuntu2_amd64.deb]`

**Remove a package:**

To remove a package using `dpkg` **without** removing its configuration files:

 `$ dpkg --**remove** [package-name]`

alternatively, use the `-r` flag:

 `$ dpkg -r [**package**-name]`

To remove a package using `dpkg` **along with** its corresponding configuration files, use the `--purge` command:

 `$ dpkg --purge [**package**-name]`

### 📄 Kali Linux Documentation

[Kali Docs | Kali Linux Documentation](https://docs.kali.org/)

[Kali Linux Forums](https://forums.kali.org/)

[Kali Tools | Kali Linux Tools](https://tools.kali.org/)

[](https://bugs.kali.org/)

[Kali Linux Revealed (KLR/PEN-103) | Mastering the Penetest Distribution](https://kali.training/)
