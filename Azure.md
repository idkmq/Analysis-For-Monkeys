# Azure Threat Hunting

## Introduction 
 As mention before this guide by no way is not all knowing but a basic starting place and information dump on Azure cloud threat hunting broken down to concepts and some poorly put together cheatsheets.  

## Conceptualizing The Cloud

Lets begin by breaking down the idea of hunting within a cloud and items we need to consider, then we can highlight Azure specifically.

### Generic Cloud Environment
1.  **Understanding Cloud Architecture**: Know the shared responsibility model, which outlines what the cloud provider and the organization are responsible for in terms of security. This understanding is crucial for identifying where potential vulnerabilities and threats could exist.
    
2.  **Visibility and Log Management**: Ensure comprehensive logging across the environment. This includes access logs, application logs, and network traffic. The ability to aggregate, correlate, and analyze these logs is foundational for effective threat hunting.
    
3.  **Identity and Access Management (IAM)**: Focus on monitoring and analyzing authentication and authorization mechanisms. Misconfigured IAM policies are a common entry point for attackers.
    
4.  **Endpoint and Network Security**: Even in the cloud, endpoints (e.g., virtual machines) can be compromised. Network security measures, including segmentation and traffic analysis, are vital.
    
5.  **API Security**: APIs are the backbone of cloud services. Monitoring API usage for abnormal patterns is essential for detecting potential threats.
    
6.  **Threat Intelligence Integration**: Use threat intelligence feeds to understand the latest threat actors and their TTPs. This helps in creating more effective hunting hypotheses.
    
7.  **Automation and Orchestration**: Leverage automation for repetitive tasks and orchestration for coordinating complex responses to detected threats.

### Azure-specific Considerations

1.  **Azure Active Directory (AD) and Identity Protection**: Focus on Azure AD for signs of compromised accounts or suspicious sign-in activities. Azure Identity Protection can automate the detection and remediation of identity-based threats.
    
2.  **Azure Monitor and Azure Security Center**: Utilize Azure Monitor for collecting and analyzing log data across Azure services. Azure Security Center provides advanced threat protection capabilities and security recommendations.
    
3.  **Network Watcher and Azure Firewall**: Use Azure Network Watcher for monitoring and diagnosing network security issues. Azure Firewall can provide insights into network traffic patterns that may indicate a threat.
    
4.  **Azure Policy and Compliance**: Regularly assess your cloud environment against Azure policies and compliance standards to ensure that misconfigurations and non-compliance issues are promptly addressed.
    
5.  **Storage Security**: Monitor access to Azure Storage accounts and use advanced threat protection to detect unusual access patterns or potential data exfiltration activities.
    
6.  **Serverless and Container Security**: Pay attention to Azure Functions and Azure Kubernetes Service (AKS), ensuring that serverless functions and containers are configured securely and monitored for suspicious activities.
    
7.  **Custom Alerts and Hunting Queries**: Utilize Azure Sentinel, Microsoft's cloud-native SIEM, to create custom alerts and hunting queries based on known or suspected threat indicators specific to your environment.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyOTk4MDUzNF19
-->