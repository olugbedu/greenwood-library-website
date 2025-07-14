# Linux Command Line & Filesystem Navigation

## Introduction

This is the Linux Filesystem Navigation and Command Line task. The project focuses on using the Linux terminal to navigate the filesystem, manipulate files/directories, and complete the Side Hustle Task using essential CLI commands.
---

## What I Used

- **Operating System**: Ubuntu 24.04 LTS (EC2 Instance)
- **Terminal**: Ubuntu default terminal
- **Linux Shell**: Bash

![](images/ubuntu.png)

---

##  Linux Command Line Basics

##  The Side Hustle Task – Step-by-Step

###  Step 1: Create Main Directory `SideHustle`

```bash
mkdir SideHustle
cd SideHustle
```

![Step 1 Screenshot](images/mkdir-cd.png)

---

###  Step 2: Create Subdirectories – `Clients`, `Projects`, `Invoices`

```bash
mkdir Clients Projects Invoices
```

![Step 2 Screenshot](images/mkdir2.png)

---

###  Step 3: Create `clients.txt` in `Clients` Folder and Add Content

```bash
touch Clients/clients.txt
echo "Client A" > Clients/clients.txt
```

![Step 3 Screenshot](images/touch-echo.png)

---

###  Step 4: Concatenate `clients.txt` in the `Clients` Folder

```bash
cat Clients/clients.txt
```

![Step 4 Screenshot](images/cat.png)

---

###  Step 5: Create `project1.txt` in the `Projects` Folder

```bash
touch Projects/project1.txt
```

![Step 5 Screenshot](images/touch-echo.png)

---

###  Step 6: Create Two Invoice Files in the `Invoices` Folder

```bash
touch Invoices/invoice1.pdf Invoices/invoice2.pdf
```

![Step 6 Screenshot](images/touch-echo.png)

---

###  Step 7: Move `clients.txt` from `Clients` to `Projects`

```bash
mv Clients/clients.txt Projects/
```

![Step 7 Screenshot](images/mv-cp-rm.png)

---

###  Step 8: Create a Backup of `project1.txt`

```bash
cp Projects/project1.txt Projects/project1_backup.txt
```

![Step 8 Screenshot](images/mv-cp-rm.png)

---

### Step 9: Delete `invoice2.pdf` from the `Invoices` Folder

```bash
rm Invoices/invoice2.pdf
```

![Step 9 Screenshot](images/mv-cp-rm.png)

---

###  Step 10: Display Final Folder Structure

```bash
tree
SideHustle/
├── Clients/                (now empty)
├── Projects/
│   ├── clients.txt
│   ├── project1.txt
│   └── project1_backup.txt
└── Invoices/
    └── invoice1.pdf
```

![Step 10 Screenshot](images/tree.png)

---

##  Linux Commands Demonstrated

| Task                          | Command(s) Used                                |
|-------------------------------|------------------------------------------------|
| Create directory              | `mkdir`                                        |
| Change directory              | `cd`                                           |
| Create file                   | `touch`                                        |
| Add content to file           | `echo`                                         |
| View file content             | `cat`                                          |
| Move or rename files          | `mv`                                           |
| Copy files                    | `cp`                                           |
| Delete files                  | `rm`                                           |
| Show folder structure         | `tree`                                         |
| List directory content        | `ls`                                           |

---
