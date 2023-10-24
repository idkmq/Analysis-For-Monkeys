## THREAT GROUP: **PHOENIX NIGHTHAWK**

**First Observed**:
Discovered by TechGuard while attempting to infiltrate financial institutions in Europe.

**Summary**:
Phoenix Nighthawk has been a looming cyber threat since 2019, heavily targeting banks and financial firms across Europe and Asia. Their modus operandi appears to be monetary gain through data theft and subsequent sale on the dark web. They've recently expanded their reach, targeting healthcare and insurance sectors in North America.

Unlike many other groups, Phoenix Nighthawk deploys ransomware attacks, holding vital company data hostage in exchange for cryptocurrency. Their operations reflect a deep understanding of their target industries.

**Target Industries**:
Banking, Financial Services, Healthcare, Insurance

**Target Countries**:
Europe (primary focus), Asia, North America

**Known Malicious File Hashes**:
[Hashes similar in structure to the ones provided in the original example]

**TTPs**:
- Deployment of memory-resident malware on Windows platforms
- Employing PowerShell scripts for lateral movement and data exfiltration
- Using WMI (Windows Management Instrumentation) for remote command execution
- Phishing campaigns with lures related to financial transactions
- Emulating legitimate Windows processes to remain undetected

## Using OODA Loop Ex.1 - **PHOENIX NIGHTHAWK**

### 1. **Observe**:

#### *Setting the Stage*:

- **Acquisition with FTK Imager**: Start by creating a forensic image of the suspect system using FTK Imager. This will allow for an in-depth examination without affecting the original data.
  
#### *Initial Observations from Intel*:

- **Memory-Resident Malware**: Since the malware is memory-resident, it might not be persistent on disk. Hence, acquiring a memory dump would be crucial.
  
- **PowerShell Scripts**: Check for recent PowerShell activity. PowerShell transcripts or logs can be insightful.
  
- **WMI Commands**: Search for any logs or artifacts suggesting the use of WMI for remote command execution.
  
- **Phishing Campaigns**: Examine email clients, browser history, and downloads for any signs of phishing lures or suspicious attachments.
  
- **Emulating Processes**: Look for processes that seem to replicate genuine Windows processes but act anomalously.

### 2. **Orient**:

#### *Understanding the Environment*:

- **File System Examination**: Using FTK Imager, explore the file system for any suspicious or recently modified files, especially in common directories known for malware persistence.
  
- **Browser and Email Analysis**: Investigate stored emails, attachments, and browser downloads.
  
- **Log Analysis**: Delve into Windows event logs, PowerShell logs, and other system logs for suspicious events.

#### *Correlation with TTPs*:

- **Memory Analysis**: Use tools like Volatility to analyze the memory dump and find signs of the memory-resident malware.
  
- **Script Examination**: Scrutinize PowerShell scripts for any known bad commands, IP addresses, or URLs.

### 3. **Decide**:

#### *Analysis Decision Points*:

- **Memory-Resident Malware Triage**: If suspicious processes or injected threads are identified in the memory dump, further investigate their origins and persistence mechanisms.
  
- **Suspicious Files**: For any suspicious files found, calculate their hashes and compare them with known IOCs (Indicators of Compromise).
  
- **Unusual Network Connections**: Based on intel, if certain domains or IP addresses are known, search for connections or requests to these addresses.

### 4. **Act**:

#### *Response and Mitigation*:

- **Containment**: If malicious artifacts are identified, consider isolating the machine from the network to prevent lateral movement or further exfiltration.
  
- **Further Analysis**: If you spot unfamiliar PowerShell scripts, consider executing them in a controlled environment to observe their behavior.
  
- **Document Findings**: Ensure you maintain a thorough record of your findings. This will be invaluable for any post-incident activities or for refining future hunt operations.
  
- **Review and Repeat**: Loop back to the "Observe" phase. With the knowledge gained from the initial analysis, re-assess and dive deeper. The OODA loop is iterative. As you uncover more evidence and intelligence, it will guide subsequent cycles.

---

Remember, the **OODA Loop** ensures a continuous cycle of understanding the situation, making informed decisions, and taking necessary actions. In cyber hunt operations, it helps keep the analysis focused and adaptive. Especially when dealing with sophisticated adversaries like "PHOENIX NIGHTHAWK", a structured approach like the OODA loop becomes invaluable.

---
## Investigating TTPS - **PHOENIX NIGHTHAWK**

### TTP: Deployment of Memory-Resident Malware on Windows platforms

**FTK Imager Action**:

-   **Memory Dump**: Use FTK Imager to capture a memory dump of the system. Analyze the dump with tools like Volatility to identify signs of the memory-resident malware. This can include searching for rogue processes, injected threads, or unlinked modules.

### TTP: Employing PowerShell Scripts for Lateral Movement and Data Exfiltration

**FTK Imager Action**:

-   **PowerShell Artifacts**: Navigate to the paths where PowerShell transcripts or logs might reside. For instance, the path `C:\Windows\System32\WindowsPowerShell\v1.0` could have profile scripts. Review these for suspicious commands or scripts.
-   **User Profiles**: Check user profile directories for PowerShell history (`C:\Users\[Username]\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadline\ConsoleHost_history.txt`) to identify recently executed commands.

### TTP: Using WMI (Windows Management Instrumentation) for Remote Command Execution

**FTK Imager Action**:

-   **WMI Persistence**: Investigate the `C:\Windows\System32\wbem\` directory for any irregular MOF (Managed Object Format) files, which might be used for WMI persistence.
-   **WMI Logs**: Check the Event Logs for WMI activity. Suspicious remote WMI executions can be uncovered this way.

### TTP: Phishing Campaigns with Lures Related to Financial Transactions

**FTK Imager Action**:

-   **User Downloads and Documents**: Navigate to typical user directories (`C:\Users\[Username]\Downloads`, `C:\Users\[Username]\Documents`) looking for recently downloaded files or documents that might be linked to phishing campaigns.
-   **Email Attachments**: If the system has a local email client (like Outlook), you can inspect the stored emails and attachments for signs of phishing. Look into PST/OST files.

### TTP: Emulating Legitimate Windows Processes to Remain Undetected

**FTK Imager Action**:

-   **System32 Directory**: Navigate to `C:\Windows\System32\` and look for files that might be out of place or mimicking genuine processes.
-   **Hash Analysis**: For any suspicious-looking executables or files, calculate their hashes using FTK Imager and compare them against the known malicious file hashes provided in the intel.

**General Best Practices**:

1.  **Timeline Analysis**: Build a timeline of file activities. It helps in pinpointing suspicious actions, especially if you have a specific timeframe of the potential compromise.
2.  **Known File Filter (KFF)**: Utilize KFF in FTK to filter out known good files and narrow down your list of potential items to review.
3.  **Recycle Bin**: Don't forget to inspect the Recycle Bin for any deleted files that might be relevant.
4.  **Slack Space and Unallocated Space**: Examine these areas for remnants of files or data that could be tied to the TTPs.
5.  **External Connections**: Review the system's browser history, cached DNS entries, and other networking-related artifacts for potential command & control communication or other malicious network activity.

Remember, FTK Imager provides a snapshot of the filesystem and system state. While it's an invaluable tool for digital forensics, pairing it with dynamic analysis tools and contextual intelligence (like the provided TTPs) often results in the most effective investigations.

---
## THREAT GROUP: **RUBY SPARROW**

**First Observed**:
2020; Identified by NetSentinel after a series of attacks on telecommunications providers in Asia-Pacific.

**Summary**:
Ruby Sparrow surfaced in 2020 with a clear focus on telecommunications networks in the Asia-Pacific region. Their intent seems to be espionage, gathering intelligence and possibly preparing the battleground for state-sponsored actors. Recent activities suggest they might be branching out to target satellite communication providers globally.

Ruby Sparrow is known for its meticulous approach, often remaining undetected for extended periods, leveraging zero-day vulnerabilities and sophisticated malware.

**Target Industries**:
Telecommunications, Satellite Communications

**Target Countries**:
Asia-Pacific (primary focus), Middle East, Europe, North America

**Known Malicious File Hashes**:
[Hashes similar in structure to the ones provided in the original example]

**TTPs**:
- Exploiting zero-day vulnerabilities in Windows server systems
- Utilizing DNS tunneling for covert data exfiltration
- Using encrypted payloads to bypass traditional security measures
- Deploying rootkits for deep persistence
- Mimicking legitimate telecommunication software processes

---

## THREAT GROUP: **SILVER PUMA**

**First Observed**:
2017; Uncovered by CyberNexa during a series of breaches in aerospace and defense companies in North America.

**Summary**:
Silver Puma emerged in 2017, targeting primarily aerospace and defense sectors. Their attacks hint at espionage, possibly backed by a nation-state given their high level of sophistication. They seem particularly interested in stealth technologies and next-gen aviation solutions.

They are known for deploying multi-staged attacks, leveraging both Windows-based systems and IoT devices within an organization's network.

**Target Industries**:
Aerospace, Defense, Aviation

**Target Countries**:
North America (primary focus), Europe, Middle East

**Known Malicious File Hashes**:
[Hashes similar in structure to the ones provided in the original example]

**TTPs**:
- Utilizing spear-phishing campaigns targeting senior engineers
- Employing Windows-based RATs (Remote Access Trojans) for initial access
- Leveraging IoT vulnerabilities for lateral movement within networks
- Deploying UEFI (Unified Extensible Firmware Interface) rootkits for deep system persistence
- Masquerading as common network management tools

---
