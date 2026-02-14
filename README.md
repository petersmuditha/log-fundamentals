# **Log analays in Digital Forencies**

> A personal deep dive into logging mechanisms, formats, and analysis across Windows and Linux systems.

## 📌 Description
This repository contains my notes, scripts, and examples from studying system and application logging. I explore where logs are stored, how to read them, and how to use them for troubleshooting and security monitoring.

## 🧠 What I Learned
- **Use Cases of Logs**
- **Types of Logs**
- **Introduction to Windows Logging System**
- **Web Server Log Analysis Guide**:
  
## 📁 Repository Structure
  Log analays in Digital Forencies/
├── Problems I Solved
│ ├── Use Cases of Logs
│ └── Types of Logs
├── Introduction to Windows Logging System
│ ├──  Web Server Log Analysis Guide

## 🐛 Problems I Solved
While analyzing web server logs, I used cat to combine two log files but accidentally overwrote one of them. Instead of using cat access1.log access2.log > combined.log, I mistakenly used cat access1.log > access2.log, which replaced the contents of access2.log with access1.log, causing data loss. To recover, I realized I had a backup of the original logs in a compressed archive. I restored the files using tar -xzf backup_logs.tar.gz and then properly combined them with cat access1.log access2.log > combined.log to avoid overwriting. This taught me to always double-check redirection targets and maintain backups.

# **Use Cases of Logs** 🎯

🔒 Security Events Monitoring	Logs help us detect anomalous behavior when real-time monitoring is used.
🔍 Incident Investigation and Forensics	Logs are the traces of every kind of activity. It offers detailed information on what happened during the incident. The security team utilizes the logs to perform root cause analysis of incidents.
🛠️ Troubleshooting	As the logs also record the errors in systems or applications, they can be used to diagnose issues and helpful in fixing them.
📊 Performance Monitoring	Logs can also provide valuable insights into the performance of applications.
📝 Auditing and Compliance	Logs play a major role in Auditing and Compliance, making it easier with its capability to establish a trail of different kinds of activities.
This room will equip you with an understanding of various types of logs maintained in different systems. We will also be practically investigating logs as traces of different attacks.

# **Types of Logs** 📁
Logs are segregated into multiple categories according to the type of information they provide. So now you just need to look into the specific log file for which the issue relates.

For example: You need to investigate the successful logins from yesterday at a specific timeframe in Windows OS. Instead of looking into all the logs, you only need to see the system's Security Logs to find the login information. We also have other types of logs that are useful in investigating different incidents. Let's have a look at them.

💻 System Logs
Usage: The system logs can be helpful in troubleshooting running issues in the OS. These logs provide information on various operating system activities.

Examples:

System Startup and shutdown events

Driver Loading events

System Error events

Hardware events

🔒 Security Logs
Usage: The security logs help detect and investigate incidents. These logs provide information on the security-related activities in the system.

Examples:

Authentication events

Authorization events

Security Policy changes events

User Account changes events

Abnormal Activity events

📱 Application Logs
Usage: The application logs contain specific events related to the application. Any interactive or non-interactive activity happening inside the application will be logged here.

Examples:

User Interaction events

Application Changes events

Application Update events

Application Error events

📝 Audit Logs
Usage: The Audit logs provide detailed information on the system changes and user events. These logs are helpful for compliance requirements and can play a vital role in security monitoring as well.

Examples:

Data Access events

System Change events

User Activity events

Policy Enforcement events

🌐 Network Logs
Usage: Network logs provide information on the network's outgoing and incoming traffic. They play crucial roles in troubleshooting network issues and can also be handy during incident investigations.

Examples:

Incoming Network Traffic events

Outgoing Network Traffic events

Network Connection Logs

Network Firewall Logs

🔑 Access Logs
Usage: The Access logs provide detailed information about the access to different resources. These resources can be of different types, providing us with information on their access.

Examples:

Webserver Access Logs

Database Access Logs

Application Access Logs

API Access Logs

⚠️ Note: There can be various other types of logs depending on the different applications and the services they provide

# **Introduction to Windows Logging System**
Like other operating systems, Windows OS also logs many of the activities that take place. These are stored in segregated log files, each with a specific log category. Some of the crucial types of logs stored in a Windows Operating System are:

📁 Key Windows Log Categories
Log Type	Purpose	Example Content
📱 Application Logs	Applications running on the OS	Errors, warnings, compatibility issues
⚙️ System Logs	Operating system operations	Driver issues, hardware issues, system startup/shutdown
🔒 Security Logs	Security-related activities	User authentication, account changes, policy changes
Besides these, several other log files in the Windows operating system are designed for logging activities related to specific actions and applications.

# **Event Viewer: Windows Log Analysis Tool 🔍**
Unlike other log files studied in the previous tasks, which had no built-in application to view them, Windows OS has a utility known as Event Viewer, which gives a nice graphical user interface to view and search for anything in these logs.

![image alt](https://github.com/petersmuditha/log-fundamentals/blob/af25df8019845d96d2a9e1487a50c189eede0752/Cattura300.PNG)

# ** How to Access Event Viewer **:
Click the Start button 🏠

![image alt](https://github.com/petersmuditha/log-fundamentals/blob/539a85e29c9f5f2df7786628a95f5cfa25522d39/Cattura350.PNG)

Type 'Event Viewer' ⌨️

![image alt](https://github.com/petersmuditha/log-fundamentals/blob/aeefa182e88a5051f609d01d207081ab1405a622/Cattura351.PNG)

Press Enter ⏎

![image alt](https://github.com/petersmuditha/log-fundamentals/blob/cdf58f85410b613be038faf81c7810ec379ecee4/Cattura352.PNG)

The highlighted area in the screenshot above shows the different available logs. You can click 'Windows Logs' from the highlighted section to see the different types of logs we discussed at the beginning of this task.

# **Understanding Windows Event Log Structure** 📊

Major Event Log Fields:

### 1. 📝 Description	Detailed information of the activity	Contains the full context of what happened
### 2.📁 Log Name	Indicates the log file name	Tells you which log category this belongs to
### 3.🕐 Logged	Time of the activity	Crucial for timeline reconstruction
### 4.🔢 Event ID	Unique identifier for specific activity	The key to filtering and searching

# **Crucial Windows Event IDs 🎯**
Numerous event IDs are available in Windows event logs. We can use these event IDs to search for any specific activity. For example, event ID 4624 uniquely identifies the activity of a successful login.

Event ID	Description	Security Significance
### 1.✅ 4624	A user account successfully logged in	Monitor successful authentications
### 2.❌ 4625	A user account failed to login	Detect brute force attacks
### 3.🚪 4634	A user account successfully logged off	Track session management
### 4.👤 4720	A user account was created	Detect unauthorized account creation
### 5.🔑 4724	An attempt made to reset an account's password	Monitor password reset attempts
### 6.🟢 4722	A user account was enabled	Track account status changes
### 7.🔴 4725	A user account was disabled	Monitor account deactivations
### 8.🗑️ 4726	A user account was deleted	Detect account removal
⚠️ Note: There are many more event IDs. It is not necessary to remember all of them, but it is good to remember the crucial event IDs.

# **Filtering Logs in Event Viewer 🔎**
Event Viewer allows us to search for the logs related to a specific event ID with its 'Filter Current Log' feature.

Steps to Filter Logs:

Navigate to desired log category 📁

![image alt](https://github.com/petersmuditha/log-fundamentals/blob/1c38e9add71a266fff28b3e80215e398521a1d8b/Cattura353.PNG)

Click 'Filter Current Log' ⚙️

![image alt](https://github.com/petersmuditha/log-fundamentals/blob/1c38e9add71a266fff28b3e80215e398521a1d8b/Cattura354.PNG)

Enter Event IDs (e.g., 4624,4625)

![image alt](https://github.com/petersmuditha/log-fundamentals/blob/1c38e9add71a266fff28b3e80215e398521a1d8b/Cattura355.PNG)

Click 'OK' ✅

## Web Server Log Analysis Guide 🌐
Introduction to Web Server Logs
We interact with many websites daily. Sometimes, we just want to view the website, and sometimes, we want to log in or upload a file into any available input field. These are just different kinds of requests we make to a website. All these requests are logged by the website and stored in a log file on the web server running that website.
This log file contains all the requests made to the website along with the information on the timeframe, the IP requested, the request type, and the URL.

# 1. cat Command - Display Log Contents
![image alt](https://github.com/petersmuditha/log-fundamentals/blob/6e7d970365bebb0f51bc4b91bbfc4c28ea656d27/Cattura400.PNG)

Description: 📄
The cat command displays the entire contents of a text file. In log analysis, it's used to view raw log data.

# 2. cat with Multiple Files - Combine Logs

![image alt](https://github.com/petersmuditha/log-fundamentals/blob/6e7d970365bebb0f51bc4b91bbfc4c28ea656d27/Cattura401.PNG)

Description: 🔗
Combines multiple log files into one. Useful when logs are rotated or split across different files.

Process:

Reads access1.log

Reads access2.log

Outputs combined content to combined_access.log

Use Case: Analyzing logs from different time periods together.

# 3. grep Command - Search for Specific Patterns
   
![image alt](https://github.com/petersmuditha/log-fundamentals/blob/6e7d970365bebb0f51bc4b91bbfc4c28ea656d27/Cattura402.PNG)

Description: 🔍
Searches for specific text patterns within log files. In this case, finds all entries from IP 192.168.1.1.

# 4. less Command - Paginated Log Viewing
![image alt](https://github.com/petersmuditha/log-fundamentals/blob/6e7d970365bebb0f51bc4b91bbfc4c28ea656d27/Cattura403.PNG)

Description: 📖
Displays log files one page at a time, preventing information overload from large files.

# Conclusion
This investigation demonstrated how digital forensics transforms digital footprints into courtroom evidence. Through meticulous log analysis, metadata extraction, and proper forensic protocols, hidden digital traces were uncovered and linked to criminal activity. The case proves that digital evidence is both powerful and decisive when collected and analyzed with precision. The right tools, proper methodology, and attention to detail turn chaotic data into clear, actionable intelligence for justice.
