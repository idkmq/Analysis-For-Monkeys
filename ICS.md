# ICS with IT network

In modern industrial environments, Industrial Control Systems (ICS) and Information Technology (IT) networks are often interconnected to facilitate data exchange and remote control capabilities. This integration of IT and ICS networks can present additional cybersecurity challenges, as an attack on the IT network could potentially affect the ICS network and vice versa. Therefore, ICS defense must include measures to protect both the ICS and IT networks.

Here are some key components of an ICS defense that includes the IT network:

- Network Segmentation: Segmentation of the IT and ICS networks is critical to minimize the risk of attacks spreading between the networks. This can be achieved by implementing firewalls, routers, and other network security devices to control the flow of traffic between different network segments.

- Vulnerability Management: Regular vulnerability assessments should be conducted on both the IT and ICS networks to identify potential weaknesses that could be exploited by attackers. Vulnerability management programs should include regular scanning, patching, and updating of software and hardware components.

- Access Control: Access control measures should be implemented to restrict access to IT and ICS networks to authorized personnel only. This can include user authentication and authorization, physical security measures, and privileged access management.

- Monitoring and Detection: Continuous monitoring and detection capabilities are critical to identifying and responding to cyber threats in a timely manner. This can include intrusion detection and prevention systems, network traffic analysis, and security information and event management (SIEM) systems.

- Incident Response: A well-defined incident response plan should be in place to provide a rapid and effective response to cyber incidents. This plan should include procedures for identifying and containing the incident, assessing the impact, and restoring normal operations.

- Training and Awareness: All personnel with access to the IT and ICS networks should be trained on the importance of cybersecurity and aware of the potential risks and threats. This can include regular security awareness training, phishing simulations, and incident response drills.

# Lateral Movement from IT to ICS 

Lateral movement refers to the technique used by attackers to move laterally within a network after gaining initial access to it. In the context of ICS security, lateral movement can occur when attackers gain access to the IT network and then attempt to move laterally into the ICS network.

Here are some common methods used by attackers for lateral movement between IT and ICS networks:

- Stolen Credentials: Attackers can use stolen credentials to gain access to the IT network, and then use those same credentials to move laterally into the ICS network.

- Malware: Attackers can use malware to infect a computer or device on the IT network and then use that infected device as a launching point to move laterally into the ICS network.

- Remote Access: Attackers can use remote access tools or backdoors to gain access to the IT network, and then use those tools to move laterally into the ICS network.

- Weak Network Segmentation: If the IT and ICS networks are not properly segmented, an attacker who gains access to the IT network may be able to move laterally into the ICS network.

To prevent lateral movement between IT and ICS networks, organizations should consider the following measures:

- Implement Strong Authentication: Implement strong authentication measures such as multi-factor authentication and privileged access management to reduce the risk of stolen credentials being used for lateral movement.

- Regularly Monitor for Malware: Regularly monitor for malware on both the IT and ICS networks to detect and respond to infections before attackers can use them for lateral movement.

- Secure Remote Access: Implement secure remote access controls, such as VPNs and secure gateways, to prevent unauthorized access to the IT network.

- Proper Network Segmentation: Properly segment the IT and ICS networks to reduce the risk of lateral movement between the networks.

- Conduct Regular Security Assessments: Regularly conduct security assessments to identify weaknesses in the IT and ICS networks that could be exploited for lateral movement.

By implementing these measures, organizations can reduce the risk of lateral movement between IT and ICS networks and enhance the overall security posture of their industrial systems.

# Common ICS protocols 

| Protocol     | Port(s)       | Description |
| ------------ | -------------| ----------- |
| Modbus       | 502/tcp, 502/udp | A serial communication protocol commonly used in industrial environments for communication between electronic devices. It is used for controlling and monitoring devices such as programmable logic controllers (PLCs), remote terminal units (RTUs), and sensors. |
| DNP3         | 20000/tcp     | A protocol used in the utility industry for communication between control systems and remote devices such as substations, RTUs, and intelligent electronic devices (IEDs). It is used for data acquisition, control, and monitoring of devices. |
| OPC          | 135/tcp, 135/udp,  OPC-UA: 484/tcp, 484/udp | A protocol used for exchanging data between industrial control systems and devices. OPC-UA is a newer version that supports secure and reliable communication. |
| Ethernet/IP  | 44818/tcp, 44818/udp | A protocol used in automation and control systems for communication between devices on an Ethernet network. It is used for controlling and monitoring devices such as PLCs, robots, and sensors. |
| Profinet     | 20547/tcp    | A protocol used for real-time communication between automation systems and devices. It is used for controlling and monitoring devices such as PLCs, drives, and sensors. |
| BACnet       | 47808/tcp,  BACnet/IP: 47808/udp | A protocol used for building automation and control networks. It is used for controlling and monitoring devices such as HVAC systems, lighting systems, and access control systems. |
| CAN          | N/A          | A protocol used in automotive and industrial applications for communication between electronic devices. It is used for controlling and monitoring devices such as engine control units (ECUs), sensors, and actuators. |
| Zigbee       | 80/tcp, 443/tcp, 1883/tcp, 8883/tcp | A wireless protocol used for communication between low-power devices such as sensors, controllers, and actuators. It is used in home automation, industrial control, and healthcare applications. |


## Protocol Attack Vectors

| Protocol | Possible Exploits |
| -------- | ---------------- |
| Modbus   | Replay attacks, buffer overflows, man-in-the-middle attacks, unauthorized commands, firmware exploits. |
| DNP3     | Man-in-the-middle attacks, unauthorized commands, remote code execution, protocol fuzzing. |
| OPC      | Protocol fuzzing, unauthorized access, denial-of-service attacks. |
| Ethernet/IP | Denial-of-service attacks, man-in-the-middle attacks, spoofing attacks, buffer overflow exploits. |
| Profinet | Denial-of-service attacks, man-in-the-middle attacks, unauthorized access, firmware exploits. |
| BACnet   | Unauthorized access, denial-of-service attacks, protocol fuzzing, buffer overflow exploits. |
| CAN      | Message injection attacks, firmware exploits, denial-of-service attacks. |
| Zigbee   | Eavesdropping, jamming, replay attacks, firmware exploits. |


# Common ICS Devices 
| Device | Description |
| ------ | ----------- |
| PLC (Programmable Logic Controller) | A digital computer used in industrial automation and control systems to monitor and control machinery and processes. It receives inputs from sensors and other devices, processes the inputs based on a programmed logic, and generates outputs to control actuators and other devices. |
| RTU (Remote Terminal Unit) | A device used in industrial control systems to monitor and control field devices such as pumps, valves, and sensors. |
| HMI (Human-Machine Interface) | A device or software application used in industrial control systems to display process information to the operator and enable the operator to control the process. It often includes a graphical interface with buttons, switches, and indicators. |
| SCADA (Supervisory Control and Data Acquisition) | A system used in industrial control systems to monitor and control remote devices such as pumps, valves, and sensors. It typically includes a central computer or server, communication networks, and field devices such as RTUs and PLCs. |
| DCS (Distributed Control System) | A system used in industrial control systems to control and monitor distributed processes, such as chemical processes, power generation, and oil refining. It typically includes multiple controllers distributed across the process and a central operator interface. |
| MES (Manufacturing Execution System) | A system used in manufacturing processes to manage and monitor production processes, such as scheduling, resource allocation, and quality control. It typically includes a central computer or server and communication networks to interface with machines and equipment. |
| IED (Intelligent Electronic Device) | A device used in utility control systems, such as power distribution and transmission, to monitor and control remote devices such as circuit breakers, transformers, and generators. It often includes communication capabilities to interface with other devices and systems. |
| Sensor | A device used in industrial control systems to detect and measure physical or chemical characteristics, such as temperature, pressure, and flow rate. It typically generates an electrical signal that is used by other devices in the control system. |
| Actuator | A device used in industrial control systems to control a physical process, such as opening or closing a valve or adjusting the speed of a motor. It typically receives an electrical signal from another device in the control system. |

## Common ICS Devices and Their Protocols

| Device | Protocols |
| ------ | --------- |
| PLC (Programmable Logic Controller) | Modbus, Profinet, EtherNet/IP, DeviceNet, CC-Link |
| RTU (Remote Terminal Unit) | DNP3, Modbus, IEC 60870-5 |
| HMI (Human-Machine Interface) | OPC, BACnet, Modbus TCP, EtherNet/IP |
| SCADA (Supervisory Control and Data Acquisition) | Modbus, DNP3, IEC 60870-5, OPC UA |
| DCS (Distributed Control System) | Foundation Fieldbus, HART, Profibus, EtherNet/IP |
| MES (Manufacturing Execution System) | B2MML, ISA-95, OPC UA |
| IED (Intelligent Electronic Device) | IEC 61850, DNP3, Modbus |
| Sensor | HART, Foundation Fieldbus, Profibus, DeviceNet |
| Actuator | Profibus, AS-Interface, Modbus TCP |

## Common ICS Devices and Vendors/Models
| Device | Top 10 Vendors | Top 10 Models |
|---|---|---|
| Programmable Logic Controllers (PLCs) | Allen-Bradley, Siemens, Schneider Electric, Omron, Rockwell Automation | ControlLogix, CompactLogix, SLC 500, MicroLogix, AutomationDirect Productivity Series |
| Distributed Control Systems (DCSs) | Honeywell, Yokogawa, ABB, Emerson Process Management, Schneider Electric | Experion PKS, Foxboro DCS, System 800xA, DeltaV, Wonderware System Platform |
| Human-Machine Interfaces (HMIs) | Wonderware, Inductive Automation, CODESYS, Ignition, Rockwell Automation | InTouch, Ignition, CODESYS Runtime Expert, Vijeo Designer, RSView |
| Remote Terminal Units (RTUs) | Honeywell, Yokogawa, ABB, Emerson Process Management, Schneider Electric | TDC5000, Centum VP, System 900, DeltaV RTU, PACSystems RTU |
| Intelligent Electronic Devices (IEDs) | Siemens, Schneider Electric, ABB, Eaton, Emerson Electric | Siprotec, Harmony, Safelinx, Easergy P3, D2000 |
| Sensors | Honeywell, Siemens, Schneider Electric, Omron, Rockwell Automation | Solstice, Simatic, Modbus, ProCon, CompactLogix |

## Common ICS Venders and Protocols

| Vendor | Protocols |
|---|---|
| Allen-Bradley | DeviceNet, ControlNet, EtherNet/IP, Modbus, Profibus |
| Siemens | Profibus, Profinet, Modbus, IEC 61131-3, OPC UA |
| Schneider Electric | Modbus, Profibus, Profinet, OPC UA |
| Omron | DeviceNet, EtherNet/IP, Modbus, FINS, OPC UA |
| Rockwell Automation | DeviceNet, ControlNet, EtherNet/IP, Modbus, OPC UA |
| Honeywell | DeviceNet, ControlNet, EtherNet/IP, Modbus, OPC UA |
| Yokogawa | HART, FOUNDATION Fieldbus, Profibus, Modbus, OPC UA |
| ABB | HART, FOUNDATION Fieldbus, Profibus, Modbus, OPC UA |
| Emerson Process Management | HART, FOUNDATION Fieldbus, Profibus, Modbus, OPC UA |
| B&R Industrial Automation | OPC UA, CODESYS, Modbus, EtherNet/IP |

## Common ICS Devices Attacks 

| Device | Possible Exploits |
| ------ | ---------------- |
| PLC (Programmable Logic Controller) | Default credentials, insecure communication, unauthorized access, buffer overflows, firmware manipulation, ladder logic manipulation |
| RTU (Remote Terminal Unit) | Default credentials, insecure communication, unauthorized access, buffer overflows, firmware manipulation, denial of service (DoS) |
| HMI (Human-Machine Interface) | Default credentials, insecure communication, unauthorized access, cross-site scripting (XSS), SQL injection, insecure file uploads |
| SCADA (Supervisory Control and Data Acquisition) | Default credentials, insecure communication, unauthorized access, buffer overflows, command injection, SQL injection, logic manipulation, DoS |
| DCS (Distributed Control System) | Default credentials, insecure communication, unauthorized access, buffer overflows, command injection, DoS |
| MES (Manufacturing Execution System) | Default credentials, insecure communication, unauthorized access, SQL injection, command injection |
| IED (Intelligent Electronic Device) | Default credentials, insecure communication, unauthorized access, buffer overflows, firmware manipulation, command injection |
| Sensor | Insecure communication, unauthorized access, sensor tampering, sensor signal manipulation |
| Actuator | Insecure communication, unauthorized access, actuator tampering, actuator signal manipulation |
