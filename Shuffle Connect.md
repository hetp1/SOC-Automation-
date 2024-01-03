Shuffle (SOAR) Platform

Security Orchestration Automation  Response (SOAR)

*Shuffle will send alerts to TheHive and then will send an email to SOC Analyst(you) via Email

Connect Shuffle to Wazuh Manager via Root 

        nano /var/ossec/etc/ossec.conf

Edit file under global tag

      
    <integration>
    <name>shuffle</name>
    <hook_url>((input your shuffle url))</hook_url>
    <rule_id>100002</rule_id>
    <alert_format>json</alert_format>
    </integration>


Connected Successfully:
![Screenshot 2024-01-02 155608](https://github.com/hetp1/SOC-Automation-/assets/108355131/30e86c8f-f41d-4aa3-b2a3-3c708ab94d35)


Workflow to be created:
1. Mimikatz Alert Sent to Shuffle
2. Shuffle Receives Mimikatz Alerts (Extracts SHA256 Hash From File)
3. Check the Reputation Score on VirusTotal
4. Send Detail to TheHive to Create Alert
5. Send an Email to SOC Analyst(you) to Begin the Investigation

Change Me - Create a regex to parse the sha256 value in order to send to VirusTotal
![Screenshot 2024-01-02 160953](https://github.com/hetp1/SOC-Automation-/assets/108355131/171b467b-3185-440c-8d60-925020ff93ae)


Create a VirusTotal account to get API for Shuffle configuration
Upload your API key in Shuffle / change settings to SHA256 Regex and change URL for VirusTotal to get the correct hash report

Connect VirusTotal to TheHive and make sure to in put API

![Screenshot 2024-01-02 190938](https://github.com/hetp1/SOC-Automation-/assets/108355131/8b662e45-290d-404b-9ea7-83627cc4a211)



![Screenshot 2024-01-02 204734](https://github.com/hetp1/SOC-Automation-/assets/108355131/6dee3822-7490-4bad-93e2-b1c4ce382e9c)


Test and Execute Mimikatz detection

![Screenshot 2024-01-02 205001](https://github.com/hetp1/SOC-Automation-/assets/108355131/b8fbb50a-e020-49b8-b570-890a8b7c5719)

![Screenshot 2024-01-02 205230](https://github.com/hetp1/SOC-Automation-/assets/108355131/528ae982-9569-47db-b9fa-65b2f61cb4d2)


Final Workflow: (Sends email alert)

![Screenshot 2024-01-02 210209](https://github.com/hetp1/SOC-Automation-/assets/108355131/6997f220-dba5-4a23-92c2-7f1d53202a54)

