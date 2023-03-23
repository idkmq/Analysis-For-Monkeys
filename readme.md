# Host-Analysis-For-Monkeys

## Intro 
Host Analysis For Monkeys is a personal project covering the basics on how to preform analysis on a machine and the methodology needed to conduct hunts.

## Hunt Methodology 
The OODA loop (Observe, Orient, Decide, Act) is a four-step approach to decision-making that focuses on filtering available information, putting it in context and quickly making the most appropriate decision while also understanding that changes can be made as more data becomes available.

## Hunt Preplanning 

During the pre-planning phase of a hunt, analysts should thoroughly analyze the expected events and perform an OSR (Operational Security Review) on TTPs (Tactics, Techniques, and Procedures). At this stage, analysts should consider the tools available for the hunt and develop lines of investigation accordingly. If any new TTPs are identified during the mission pre-planning phase, analysts should investigate them further until they have a solid understanding, which will aid them in their hunt. It's essential to use available resources and collaborate with other analysts to refine new hunting methodologies. Being well-prepared with a clear idea of where and how to start the analysis is crucial for a successful hunt.  


## Common Persistnec Methods 

There are many  persistence methods that can be used to maintain access to a compromised system. Here are some common ones:
| Persistence Method                  | Description                                                                                                                         |
|-------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Cron jobs                           | These are scheduled tasks that run at specified times and can be used to execute malicious code.                                    |
| Startup scripts                     | These are scripts that are executed during the system boot process, and can be used to launch malicious code at startup.            |
| Backdoor accounts                   | These are user accounts with elevated privileges that are created by attackers, which can be used to maintain access to the system. |
| Malware/rootkits                    | Malicious software that can hide its presence on the system and provide remote access to the attacker.                              |
| Modified system binaries            | Attackers can modify system binaries such as login screens, SSH servers, or kernel modules to allow backdoor access.                |
| Hidden files                        | Attackers can hide malicious files in non-standard locations on the system, making it harder to detect them.                        |
| SSH keys                            | Attackers can create SSH keys that allow them to authenticate without a password, making it easier to access the system remotely.   |
| Modified system configuration files | Attackers can modify system configuration files such as /etc/passwd or /etc/shadow to create new accounts or modify existing ones.  |
| DNS hijacking                       | Attackers can modify DNS settings on the system to redirect network traffic to a malicious server.                                  |

| Persistence Method                                   | Description                                                                                                                                 |
|------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| Startup folder                                       | Programs can be added to the startup folder in the Start Menu to execute automatically when a user logs on.                                 |
| Registry Run keys                                    | Programs can be added to the Windows registry in the Run key to execute automatically when the system starts up.                            |
| Services                                             | Malicious services can be installed on the system to execute code in the background.                                                        |
| Scheduled tasks                                      | Scheduled tasks can be created to execute code at specific times, such as during system startup or when a user logs on.                     |
| Windows Management Instrumentation (WMI) persistence | WMI allows for the creation of event filters and consumer bindings, which can be used to execute code when specific events occur.           |
| COM hijacking                                        | Malicious code can be injected into legitimate Component Object Model (COM) objects, allowing them to execute code when the object is used. |
| DLL hijacking                                        | Malicious code can be injected into legitimate Dynamic Link Libraries (DLLs), allowing them to execute code when a program loads the DLL.   |
| Alternate data streams (ADS)                         | Malicious code can be hidden in an ADS attached to a legitimate file, allowing it to execute when the file is opened.                       |
| Malware/rootkits                                     | Malicious software that can hide its presence on the system and provide remote access to the attacker.                                      |

It's important to note that there are many other methods that attackers can use to maintain persistence on a compromised system, and the above list is not exhaustive. Regular system audits, monitoring, and vulnerability assessments can help detect and prevent these attacks.

## Commonly Abused DLLs

| DLL Name     | Description                                                                                                                                                |
|--------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
| kernel32.dll | Contains functions for memory management, process management, and exception handling. Used for loading and executing additional DLLs.                      |
| user32.dll   | Contains functions for creating and managing windows and user interface elements. Can be abused to execute code in the context of a logged-in user.        |
| advapi32.dll | Contains functions for managing security, including authentication and authorization. Can be abused to escalate privileges or bypass security controls.    |
| ntdll.dll    | Contains low-level system functions, including system calls and memory allocation. Can be abused to execute code with system-level privileges.             |
| msvcrt.dll   | Contains functions for input/output operations, including file and console I/O. Can be abused to execute code with elevated privileges.                    |
| comctl32.dll | Contains functions for creating and managing common controls, such as buttons and menus. Can be abused to execute code in the context of a logged-in user. |
| ole32.dll    | Contains functions for creating and managing COM objects. Can be abused to execute code in the context of a logged-in user or with elevated privileges.    |

Note that this is not an exhaustive list and attackers may use other DLLs to achieve their goals. It's important to regularly monitor system activity and be aware of common attack methods in order to detect and prevent these attacks.


## Commonly Abused Windows Binaries
| Binary Name                           | Description                                                                                                                         |
|---------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| regsvr32.exe                          | Used to register and unregister COM DLLs, but can be abused to execute malicious scripts or code.                                   |
| rundll32.exe                          | Used to load DLLs and execute their functions, but can be abused to execute malicious DLLs or code.                                 |
| mshta.exe                             | Used to execute HTML applications, but can be abused to execute malicious scripts or code.                                          |
| cscript.exe and wscript.exe           | Used to execute Windows Script Host scripts, but can be abused to execute malicious scripts or code.                                |
| powershell.exe and powershell_ise.exe | Powerful command-line shells that allow for automation and scripting, but can be abused to execute malicious scripts or code.       |
| schtasks.exe                          | Used to create and manage scheduled tasks, but can be abused to execute malicious code.                                             |
| reg.exe                               | Used to manage the Windows registry, but can be abused to execute malicious scripts or code.                                        |
| cmd.exe                               | Command-line interpreter that can be used to execute commands and scripts, but can be abused to execute malicious commands or code. |
| mmc.exe                               | Used to open Microsoft Management Console snap-ins, but can be abused to execute malicious snap-ins or code.                        |


# Outline 

- Basic Hunt Checks 
  - Windows 
    - Regs
    - schtasks
    - services 
  - Linux 
    - cronjobs 
    - services 
  - pre made queries/daily checks

- Event IDS

- Checklist 
  - Hunt Preplanning 
  - Inventory check 
    - Hardware 
    - software
    - resources
  - Tool Check/test run 

- tools 
  - systernals
  - powershell scripts/modules 
  - nmap 
  - mapping tools

# Resources List 