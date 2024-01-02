Set up Cassandra
      
      nano /etc/cassandra/casssandra.yaml

Set Listen_address & rpc_address in Casssandra.yaml to IP address of TheHive server

Change Seed_provider IP to TheHiver servers IP (XXX.XXX.XX.XXX:7000)

    root@thehive:~# systemctl stop cassandra.service
    root@thehive:~# rm -rf /var/lib/cassandra/*
    root@thehive:~# systemctl start cassandra.service
    root@thehive:~# systemctl status cassandra.service


Set up Elastic search for data query

    nano /etc/elasticsearch/elasticsearch.yml

Change Network.host to TheHive Server IP

      root@thehive2:~# nano /etc/elasticsearch/elasticsearch.yml
      root@thehive2:~# systemctl start elasticsearch
      root@thehive2:~# systemctl enable elasticsearch
      root@thehive2:~# systemctl status elasticsearch

Chech user permissions of TheHive using 

      ls -la /opt/thp

Change permissions

      chown -R thehive:thehive /opt/thp

Changes owner to destination directories - hive user and hive group (instead of root)

Go to config file of TheHive

      nano /etc/thehive/application.conf

Change hostname to thehive's server IP and change localhost input (application.baseUrl)


Create a jvm.options file under /etc/elasticsearch/jvm.options.d and put the following configurations in that file.
-Dlog4j2.formatMsgNoLookups=true
-Xms2g
-Xmx2g

