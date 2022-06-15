Simulating an Attack
====================

The goal of this section is to emulate an attack using the nikto command, this will start scanning the webpage and showing all of the open ports and vulnerabilities that are available to be exploited.  This will trigger our watcher in elastic search to automatically enable the WAF Blocking policy to protect the environment without user intervention.

#. On the KALI Web Shell (if first shell exit out of msf5 exploit) then run the following command

     .. code-block::

       nikto -host 10.1.50.100

     .. image:: ../images/Event/Picture14.png
#. Examine the Watcher on the Kibana (this could take up-to 5 minutes before it fires)

     .. image:: ../images/Event/Picture15.png
#. If the code has correctly run what you should see in the F5 now is that it automatically changed from Transparent to Blocking by launching the ansible code via the Watcher and Logstash.
     In the F5 TMUI Security Policy List  
     
     .. image:: ../images/Event/Picture16.png

     .. image:: ../images/Event/Picture17.png
#. Re-Run the Code on the KALI Web Shell run the following command
     Note the second run of the code cannot see all of the vulnerabilities that it saw before, this is because the F5 AWAF is now Blocking that bad traffic.

     .. code-block::

       nikto -host 10.1.50.100

     .. image:: ../images/Event/Picture18.png