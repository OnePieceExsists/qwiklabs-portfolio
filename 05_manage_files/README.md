# Lab 05: Manage files with Linux commands

> **Platform:** Qwiklabs  
> **Skill Area:** Linux, Command Line, File Management  
> **Date Completed:** 22-09-2025  
> **Difficulty:** Introductory  

---

## 📝 Overview
In this lab, I practiced **Linux file and directory management** commands to organize data in the `/home/analyst` directory.  
I also used the **nano text editor** to create and edit a file documenting the changes I made.  

These tasks are essential for security analysts because well-organized directories and properly maintained files make it easier to detect issues, maintain systems, and keep data safe.  

---

## 🎯 Objectives
- Create and remove directories.  
- Move and delete files.  
- Create a new file using `touch`.  
- Edit file contents using the `nano` text editor.  

---

## 🚀 What I Did

I started by examining the initial `/home/analyst` directory structure and then worked through the tasks step by step.

### 📂 Task 1: Create a New Directory
Created a new subdirectory called `logs` inside `/home/analyst`:  

![Create logs directory](screenshots/01_create_logs.png)

---

### 🗑️ Task 2: Remove a Directory
Removed the unused `temp` directory:  

![Remove temp directory](screenshots/02_remove_temp.png)

---

### 📦 Task 3: Move a File
Moved `Q3patches.txt` from the `notes` directory into the `reports` directory:  

![Move Q3patches.txt](screenshots/03_move_q3.png)

---

### 🗑️ Task 4: Remove a File
Deleted the unused `tempnotes.txt` file from the `notes` directory:  

![Remove tempnotes.txt](screenshots/04_remove_tempnotes.png)

---

### 📝 Task 5: Create a New File
Created a new file `tasks.txt` in the `notes` directory:  

![Create tasks.txt](screenshots/05_create_tasks.png)

---

### ✏️ Task 6: Edit a File
Used the **nano** editor to add documentation to `tasks.txt`:  

![Editing tasks.txt with Nano](screenshots/06_edit_tasks.png)  
 
### 🖼️ Screenshot 7: Displaying the contents of `tasks.txt`
This screenshot shows the output of the `cat /home/analyst/notes/tasks.txt` command, verifying that the changes were saved correctly.  

![Displaying tasks.txt contents](screenshots/07_display_tasks.png)  

✅ Results

Successfully created, removed, moved, and deleted files and directories.

Created and edited a documentation file (tasks.txt) using nano.

Final /home/analyst directory matched the required structure:

home
└── analyst
    ├── logs
    ├── notes
    │   └── tasks.txt
    └── reports
        ├── Q1patches.txt
        ├── Q2patches.txt
        └── Q3patches.txt

💡 Lessons Learned

The mkdir and rm -r commands are used to create and remove directories.

The mv command moves or renames files.

The nano editor is a simple way to add or update text within files directly from the shell.

Keeping directories organized helps improve system security and analysis.

📜 Evidence

Completion screenshots are available in the screenshots/ folder:

🔗 References

Qwiklabs Lab Link: 
https://www.cloudskillsboost.google/focuses/44029868?parent=lti_session&parent=lti_session

