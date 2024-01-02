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
