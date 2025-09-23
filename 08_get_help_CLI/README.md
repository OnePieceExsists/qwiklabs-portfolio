# Lab 08: Get Help in the Command Line

> **Platform:** Qwiklabs  
> **Skill Area:** Linux, Security, Command Line, Troubleshooting  
> **Date Completed:** 23-09-2025  
> **Difficulty:** Introductory  

---

## 📝 Overview
In this lab, I practiced using **Linux help commands** such as `man`, `whatis`, and `apropos` to discover command functionality, options, and the correct commands to use for specific tasks.  
As a security analyst, knowing how to quickly find command information is crucial for troubleshooting, performing tasks efficiently, and enforcing proper system management.

---

## 🎯 Objectives
- Use `whatis` to get a brief description of a command.  
- Use `man` to explore command options in detail.  
- Use `apropos` to search for commands by keywords.  
- Identify the appropriate command to perform a task.

---

## 🚀 What I Did

### Task 1: Learn More About Commands
* I started by exploring the `cat` command. First, I used `whatis` to get a short description:

whatis cat

* Next, I used man to see more details and options for cat, including how to number non-empty output lines:

man cat

Option to number output lines: -b, --number-nonblank

* Finally, I used apropos to find the command that prints the first part of a file:

apropos -a first part file

Command found: head
![Task 1 – Description](screenshots/01_learn_command.png)

### Task 2: Explore the useradd Command

I explored useradd to learn how to set an expiration date for a temporary user:

man useradd

Option to set an expiration date: -e
![Task 2 – Description](screenshots/02_man_command.png)

### Task 3: Explore rm and rmdir Commands

I used whatis to quickly review the difference between rm and rmdir:

whatis rm
whatis rmdir

Answer: rmdir removes only empty directories.
![Task 3 – Description](screenshots/03_whatis_commands.png)

### Task 4: Determine Which Command to Use

I used apropos with keywords to find the command for creating a new group:

apropos -a create new group

Command found: groupadd
![Task 4 – Description](screenshots/04_apropos_groupadd.png)

✅ Results

Successfully used whatis for quick command descriptions.

Explored man pages to find detailed options.

Used apropos to search commands by keywords.

Identified commands: head, useradd -e, rmdir, and groupadd.

💡 Lessons Learned

whatis -provides a quick overview of commands.

man -is essential for detailed command usage and options.

apropos -helps locate commands when the exact name is unknown.

Understanding command differences (e.g., rm vs rmdir) prevents accidental errors.

📜 Evidence

Screenshots are stored in the screenshots/ folder for each task.

🔗 References

Qwiklabs Lab Link:
https://www.cloudskillsboost.google/focuses/44032745?parent=lti_session&parent=lti_session
