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
