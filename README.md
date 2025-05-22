# Cybersecurity-Portfolio
Collection of cybersecurity labs, notes, and project work as I grow my skills.

## Setting Up Basic Home Cybersecurity Lab
### In this project I built a basic cybersecurity lab using VMware Workstation and Kali Linux to practice penetration testung and network security skills in a safe enviroment.

## Tools Used 
Oracle VirtualBox (virtualization platform)

Kali Linux (penetration testing distribution)

Windows 10 VM (target practice)

Host Machine (Windows)

## Steps Taken 

### 1. Installed Virtual Box 
Downloaded and installed VirtualBox Workstation on my host machine.

### 2. Downloaded Kali Linux ISO 
Retrieved the latest Kali Linux ISO from the offical website.

### 3. Created a Kali Linux VM 
Allocated 2GB RAM, 2 CPUs, and 20GB storage.

Installed Kali Linux inside the VM and set up basic tools (nmap, metasploit, wireshark)

### 4. Set up target machine
Installed a Windows 10 VM

### 5. Created an Internal Network
Configured VirtualBox Networking to "internal network" so that VM can communicate but are not touching the Internet.

### 6. Performed Inital Scans 
Used nmap to discover open ports 

Practiced running basic vulnerability scans.



# Windows Sysmon Setup with SwiftonSecurity Config
This portion of my repo documents how to install and Configure Microsoft Sysmon on Windows machine using the popular [SwiftOnSecurity](https://github.com/SwiftOnSecurity/sysmon-config) configuration file. This is useful for security monitoring, threat hunting, and building logs for SOC analysis practice.

## What is Sysmon? 
Sysmon (System Monitor) is a Windows system service and device driver that logs system activity to the Windows Event Log; process creation, network connections, and file changes.

## Prerequisites 

- A Windows Machine (I used  a VM)
- Admin previleges on the system
- [Sysinternals Sysmon](https://docs.microsoft.com/en-us/sysinternals/downloads/sysmon)

## Installation Steps 

### 1.Download Sysmon 

Go to the offical Sysinternals page: https://docs.microsoft.com/en-us/sysinternals/downloads/sysmon

Extract the ZIP file and keep note of 'Sysmon64.exe' ( for 64-bit systems).

### 2.Download the SwiftOnSecurity Config

Visit the SwiftOnSecurity config file directly: [sysmonconfig-export.xml] (https://github.com/SwiftOnSecurity/sysmon-config/blob/master/sysmonconfig-export.xml)

- Click **"Raw"**
- Right-Click the page and selct **"Save As..."**
- Save the file as 'sysmonconfig-export.xml'


### 3.Install Sysmon with the Config File

Open **Command Prompt as Administrator**, then run : 
'''cmd 
Sysmon64.exe -accepteula -i sysmonconfig-export.xml

### Check Sysmon is running using cmd "sc query sysmon64"
- Look for **"STATE: RUNNING"**

  ### Sysmon Logs will appear in Event Viewer
  Event Viewer >
      Applications and Services Log >
          Microsoft >
              Windows >
                  Sysmon >
                      Operational
  ### Logs will be listed with Event IDs
  - Event ID 1 = Process Creation
  - Event ID 3 = Network Connection
  - Event ID 10 = Process Access 



