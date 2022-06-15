Install & Configure Logstash
============================

Logstash is a light-weight, open-source, server-side data processing pipeline that allows you to collect data from a variety of sources, transform it on the fly, and send it to your desired destination. It is most often used as a data pipeline for Elasticsearch, an open-source analytics and search engine. 

#. Access Node 1 Web Shell
     In UDF -> Ansible Security Lab -> Components -> Node 1 -> Access -> Web Shell

     .. image:: ../images/Event/Picture9.png
#. Install Logstash
     In the Node 1 Web Shell run the following command
     .. code-block::

       sudo /usr/share/logstash/bin/logstash-plugin install logstash-output-exec

     .. image:: ../images/Event/Picture10.png
#. Install Nano
     In the Node 1 Web Shell run the following command 
     
     .. code-block::

       sudo rpm -ihv https://vault.centos.org/centos/8/BaseOS/x86_64/os/Packages/nano-2.9.8-1.el8.x86_64.rpm 
#. Modify the Logstash configuration file
     In the Node 1 Web Shell run the following command
     
     .. code-block::

       sudo nano /etc/logstash/conf.d/logstash.conf
#. Add the following HTTP code (in yellow) to the input section to match below (copy yellow code and paste into web shell by holding <SHIFT> and pressing <INSERT>)
     In the Node 1 Web Shell inject the yellow code only
     
     .. code-block::
        :emphasize-lines: 11, 12, 13, 14

       input {
                tcp {
                         port => 5001
                         type => awaf
                    }
                udp {
                         port => 5002
                         type => "ipfix-f5"
                         codec => netflow
                    }
               http {
                         port => 9001
                         type => "watcher-1"
                    }
             }
#. Install Nano
     In the Node 1 Web Shell
     
     .. code-block::

       sudo rpm -ihv https://vault.centos.org/centos/8/BaseOS/x86_64/os/Packages/nano-2.9.8-1.el8.x86_64.rpm 
