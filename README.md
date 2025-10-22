# basic-command-line
This provides foundational materials and exercises for learning the basics of the Command Line Interface (CLI). It introduces essential commands and concepts that enable users to navigate file systems, manage files and directories, and execute operations efficiently.

## Launching and Exiting the Linux Terminal

1. Open **CMD** or **PowerShell** on your Windows system.  
2. Type the following command and press **Enter**:

```bash
 wsl
```
When you’re done using the terminal, type:
```bash
 exit
```
## Navigation
Linux organizes its files in a tree-like structure of directories (folders), which starts at the root directory (/). The root directory contains files and subdirectories, each of which can contain more files and subdirectories, and so on. The /home directory is where user files and personal data are stored.
Unlike Windows, which may use separate drive letters (such as C: or D:), Linux maintains a single unified file system tree, regardless of how many drives or storage devices are connected. Additional storage devices are mounted onto specific directories within this tree.

This entire structure represents the Linux file system tree.

```
 .
├── bin -> usr/bin
├── boot
│   ├── androidboot
│   ├── efi
│   ├── grub
│   ├── piboot
│   └── uboot
├── dev 
├── etc
├── home
│   ├── username1
│   │		├── Documents
│   │		└── Downloads
│   └── username2
├── host
├── lib -> usr/lib
├── lib32 -> usr/lib32
├── lib64 -> usr/lib64
├── libx32 -> usr/libx32
├── media
├── meta
│   ├── gui
│   └── snap.yaml
├── mnt
│   ├── c
│   ├── wsl
│   └── wslg
├── opt
├── proc
├── root  [error opening dir]
├── run
├── sbin -> usr/sbin
├── srv
├── sys
├── tmp
├── usr
├── var
└── writable
```
### **pwd** (Print Working Directory) 
When we first log in to our system, our current working directory is automatically set to our home directory.
The folder we are currently “standing in” is called the current working directory.

To display the current working directory, use:

```bash
$ pwd
```
Think of it as asking, ***“Where am I?”***

### **ls** (List the files and directories)
To list the files and directories in your current working directory, type:
```bash
ls
```
That’s like asking, ***“What’s here?”***

You can also specify a particular folder to list its contents. For example:
```bash
ls Documents
```


Common **ls** options
| Command | Description | Example |
|----------|--------------|----------|
| `ls -l` | List directory contents in long format (shows details such as permissions, owner, size, and date). | `ls -l`, `ls -l Downloads/` |
| `ls -a` | List all files, including hidden ones (those starting with a dot `.`). | `ls -a`, `ls -a Documents/` |
| `ls -la` | List all files in long format, including hidden ones. | `ls -la`, `ls -la Desktop/` |

### **cd** (Change Directory)
To change our working directory, or to move to a different location in the filesystem, we use the **cd** command.
You type cd followed by the path name of the directory you want to move into.

For example, let’s say we want to go into the Documents folder that we saw earlier when we listed files using ls.
We can type:
```bash
$ cd Documents/
$ pwd
/home/username/Documents
$ ls
...Listing of many, many files...
```
>[!NOTE]
> The dollar sign **`$`** is called the **shell prompt**.  
> It appears whenever the shell is ready to accept a new command or input.

>[!TIP]
>If the folder name is long, you can type the first few letters and press Tab — the terminal will auto-complete the rest of the name if it exists in that path.
