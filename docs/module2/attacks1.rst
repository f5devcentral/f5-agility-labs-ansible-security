Brute Force Attacks
===================

In cryptography, a brute-force attack consists of an attacker submitting many passwords or passphrases with the hope of eventually guessing correctly. The attacker systematically checks all possible passwords and passphrases until the correct one is found. Alternatively, the attacker can attempt to guess the key which is typically created from the password using a key derivation function.

#. Access Kali Linux through UDF Lab
     In UDF -> Ansible Security Lab -> Components -> Kali -> Access -> Web Shell
     
     .. image:: ../images/Attacks/Picture1.png
          :width: 500
#. Web Shell should auto-login, then run the following commands
     .. code-block::

       cd /home/kali
       ./hydra.sh
      
     .. image:: ../images/Attacks/Picture2.png
          :width: 600
#. Once the Script runs should output the username and password

     .. image:: ../images/Attacks/Picture3.png
          :width: 400
#. Maximize the RDP Window and Login to the Web Server using the brute forced username and password from Kali
     -  Username: admin
     -  Password: password

     .. image:: ../images/Attacks/Picture4.png
          :width: 850
#. DVWA Website once logged in should look like below

     .. image:: ../images/Attacks/Picture5.png
          :width: 850