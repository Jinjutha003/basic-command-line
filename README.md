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
>If the folder name is long, you can type the first few letters and press Tab, the terminal will auto-complete the rest of the name if it exists in that path.

#### Absolute vs. Relative Paths
We use the cd command followed by the path name of the folder we want to go to.
A path name is like the route you take through the folder structure to reach a specific folder.

There are two ways to write a path name:

An **absolute path** specifies the full address starting from the root of the filesystem.
```bash
$ cd /mnt/c/Users/username/
$ pwd
/mnt/c/Users/username/
```
A **relative path** specifies the path starting from where you currently are.

For example, if we want to go to a subdirectory called Documents inside the username folder:

:point_right: Using an absolute path:

```bash
cd /mnt/c/Users/username/Documents
```
:point_right: Using a relative path (assuming we are already in /mnt/c/Users/username/):
```bash
$ cd Documents
$ pwd
/mnt/c/Users/username/Documents
```
If we want to move up to the parent directory of Documents (back to username), we can use:
```bash
$ cd ..
$ pwd
/mnt/c/Users/username/
```
**cd** shortcuts
| Command | Description | Example |
|---------|-------------|---------|
| `cd` | Change directory. Move into a specified directory. | `cd Documents` |
| `cd ..` | Move up one level (to the parent directory). | `cd ..` |
| `cd` | Change the working directory to the home directory (`/home/yourname`). |  |
| `cd /` | Change the working directory to the root directory. | `cd /` |
| `cd -` | Change the working directory to the previous working directory. |  |
| `cd ~user_name` | Change the working directory to the home directory of `user_name`. |  |

## File Manipulation

>[!TIP]
>Using Wildcards
>Wildcards allow us to quickly specify groups of filenames based on patterns of characters.
They are very useful when you want to work with multiple files at once without typing each name individually

### **mkdir** (Create Directories)
```bash
mkdir dir1
mkdir dir1 dir2 dir3
```
This creates a new folder called `dir1` in your current working directory. You can also create multiple folders at once by listing their names: `dir1` `dir2` `dir3`

### **touch** (Create a File)
```bash
touch item1.txt
touch item1.txt item2.txt item3.txt
```
The fisrt line creates a new file called `item1.txt` in the current directory. You can also create multiple files at once by listing their names: `item1.txt` `item2.txt` `item3.txt`

:tea: Let’s do a exercise!

Create a folder called cafe_menu in your current directory.
Inside cafe_menu, create three subfolders named:

dessert
drink
food
Hint: You can create all three subfolders at once using a single command

Create files inside cafe_menu folder:
salad.txt coffee.txt cake.txt burger.txt

### **cp** (Copy Files and Directories)

We use **`cp`** to copy files and directories.

---

1. Copying a File in the Same Folder
For example, to copy `cake.txt` in the same folder:

```bash
cp cake.txt cake_copy.txt
```
2. Copying a File to Another Folder
To copy a file into another folder, for example coffee.txt into the drink/ folder:

```bash
cp coffee.txt drink/
```
3. Copying an Entire Folder
To copy a whole folder, use the -r (recursive) option.
For example, to copy the drink folder into the food folder:
```bash
cp -r drink/ food/
```
### **mv** (Move and Rename Files)
1. renaming file 
mv cake_copy.txt tart.txt
2. moving files to another folder
mv cake.txt tart.txt dessert/
mv burger.txt salad.txt food
3. moving entire folder
mv dessert/ food/ 
move it bake to current directory 
mv food/dessert/ .
Note . dot means current direcotry

### **mv** (Move and Rename Files)

The **`mv`** command is used to **move files/folders** or **rename them**.

1. Renaming a File
To rename a file, use `mv` followed by the old name and the new name:
```bash
mv cake_copy.txt tart.txt
```
This renames cake_copy.txt to tart.txt.

2. Moving Files to Another Folder
```bash
mv cake.txt tart.txt dessert/
mv burger.txt salad.txt food/
```
The first command moves cake.txt and tart.txt into the dessert folder.
The second command moves burger.txt and salad.txt into the food folder.

3.Moving an Entire Folder
To move a folder (and all its contents) to another location:

```bash
mv dessert/ food/
```
This moves the dessert folder into the food folder.
To move a folder back to the current directory, use a dot .:
```bash
mv food/dessert/ .
```
Here, the `.` (dot) refers to the current working directory.

### **rm** – Remove Files and Directories

The **`rm`** command is used to **delete files and directories**.  

1. Removing a File
To delete a single file:

```bash
rm coffee.txt
```
This removes the file coffee.txt from the current directory.

2. Removing a Folder
To delete a folder and all its contents, use the -r (recursive) option:
```bash
rm -r food/drink/
```
This deletes the folder drink (inside food folder) and everything inside it.

>[!CAUTION]
>Be careful: deleted files are **not moved to the Trash** — they >are removed permanently.

