# SOC-Automation-
Security Operations Center

Tools we will be using: 
Wazah - SIEM & XDR
TheHive - Case Management
Shuffle - SOAR 


![SOC Diagram drawio](https://github.com/hetp1/SOC-Automation-/assets/108355131/211ec9a7-1516-4cb3-828c-dff62e1acd09)

Getting Started-
1. Download and Run a New Windows VM
2. Download Sysmon

   https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon
4. Install Sysmon Modular xml file from Github

   https://github.com/olafhartong/sysmon-modular/blob/master/sysmonconfig.xml

   Powershell code to install

       .\Sysmon64.exe -i .\sysmonconfig.xml
5. Install Wazuh and create a firewall with DigitalOcean
6. Install Putty to SSH in to Wazah VM
   Commands Update and Upgrade Wazuh

             atp-get update && apt-get upgrade -y

7. Install Wazuh 4.7 in SSH
   
        curl -sO https://packages.wazuh.com/4.7/wazuh-install.sh && sudo bash ./wazuh-install.sh -a

   
