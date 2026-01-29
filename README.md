# My Azure & Active Directory Lab: Learning the Basics

## What is this project?
I built this lab to get hands-on experience with the tools used in a professional Help Desk environment. Instead of just reading about it, I wanted to actually build a "mini-company" from scratch in the cloud. 

This project shows how I set up a server, created a network, and managed a group of users (like a real IT department would).

## The Tools I Used
- **Microsoft Azure:** My "virtual office" where the server lives.
- **Windows Server 2022:** The "brain" of the operation.
- **Active Directory:** The tool I used to manage people, passwords, and permissions.
- **Remote Desktop:** How I connected to the server from my own laptop.

---

## What I Did (Step-by-Step)

### 1. Building the Server
I started by creating a Virtual Machine in Azure. Think of this as buying a new computer and plugging it into a cloud network. I had to set up the "security guards" (Network Security Groups) to make sure I could log in safely.

<p align="center">
<img src="img/01_azure_vm_status.png" height="80%" width="80%" alt="My Azure Server"/>
<br />
<em>My server is up and running in the Azure portal!</em>
</p>

---

### 2. Making the Server a "Boss" (Domain Controller)
I installed **Active Directory** to turn my server into a "Domain Controller." This means this server now controls all the users and computers in my fake company, `mario.local`. 

<p align="center">
<img src="img/03_server_manager_roles.png" height="80%" width="80%" alt="AD Setup"/>
<br />
<em>This is the dashboard showing that Active Directory is ready to go.</em>
</p>

---

### 3. Organizing the Office
I created **Organizational Units (OUs)**, which are basically just digital folders. I made separate folders for "Admins" and "Staff" so everything stays organized.

<p align="center">
<img src="img/05_ou_structure.png" height="80%" width="80%" alt="Folders"/>
<br />
<em>My folder setup for the different departments.</em>
</p>

---

### 4. Creating Users & Managing Permissions
This was the fun part! I created users (like Luigi) and practiced:
- Setting up their usernames.
- Putting them in "Groups" (so they can only see files they are allowed to see).
- Resetting passwords and unlocking accounts.

**Note:** I even ran into some login issues with my "Luigi" user, which taught me how important it is to check the "Member Of" tab and the login suffix!

<p align="center">
<img src="img/08_member_of_tab.png" height="80%" width="80%" alt="User Groups"/>
<br />
<em>Checking which groups my users belong to.</em>
</p>

---

### 5. Using the "Command Line"
I practiced using **PowerShell** to find my users quickly without clicking through menus. It’s a much faster way to see what's happening on the server.

<p align="center">
<img src="img/12_powershell_users.png" height="80%" width="80%" alt="PowerShell"/>
<br />
<em>Using simple commands to list all the users I created.</em>
</p>

---

## What I Learned
- How to set up a cloud environment from scratch.
- How to manage users and keep them in the right groups.
- **Most importantly:** I learned how to troubleshoot when things don't go as planned!
