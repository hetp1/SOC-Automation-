Sent telemetry containing Mimikatz
Trigger Mimikatz alert on Wazuh

Change ossec.config file to communicate with Windows Sysmon

Test with mimikatz on windows machine

      https://github.com/gentilkiwi/mimikatz/releases

SSH into Wazuh server and edit Archives

    root@Wazuhtest:~# cp /var/ossec/etc/ossec.conf ~/ossec-backup.conf

    root@Wazuhtest:~# nano /var/ossec/etc/ossec.conf

    root@Wazuhtest:~# systemctl restart wazuh-manager.service

    root@Wazuhtest:~# cd /var/ossec/logs/archives/

    root@Wazuhtest:/var/ossec/logs/archives# ls

    2024  archives.json  archives.log

    root@Wazuhtest:/var/ossec/logs/archives# nano /etc/filebeat/filebeat.yml
  
Archives Enabled to TRUE

    root@Wazuhtest:/var/ossec/logs/archives# systemctl restart filebeat

Re-Run the mimikatz executable and check in archives of Wazuh

![Screenshot 2024-01-02 002954](https://github.com/hetp1/SOC-Automation-/assets/108355131/b13ef49c-98d1-4ad3-b1f3-bf13d9e9796a)


Create Wazuh Security Alert

        </rule>
    <rule id="100002" level="15">
    <if_group>sysmon_event1</if_group>
    <field name="win.eventdata.originalFileName" type="pcre2">(?i)mimikatz\.exe</field>
    <description>Mimikatz Usage Detected</description>
    <mitre>
      <id>T1003</id>
    </mitre>
    </rule>

![Screenshot 2024-01-02 004402](https://github.com/hetp1/SOC-Automation-/assets/108355131/029bcdef-96ea-49e9-8fed-bbd5bab7ae50)

^Found the Level 15 Alert "Mimikatz Usage Detected Test"
