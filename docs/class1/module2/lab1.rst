Brute Force Attacks
===================

Bruce Force Attacks
*******************
In cryptography, a brute-force attack consists of an attacker submitting many passwords or passphrases with the hope of eventually guessing correctly. The attacker systematically checks all possible passwords and passphrases until the correct one is found. Alternatively, the attacker can attempt to guess the key which is typically created from the password using a key derivation function.

#. Access Kali Linux through UDF Lab
     I1.	In UDF -> Ansible Security Lab -> Components -> Kali -> Access -> Web Shell
       .. image:: ../images/Picture2.png
#. Login to BIG-IP Webpage
     -  Username: admin
     -  Password: admin123

       .. image:: ../images/Picture3.png
#. Ensure that the BIG-IP Is licensed, if it is you should see that its Online and Active, if its marked Offline with RED and doesn’t change or has a message about licensing being bad, you can try scrolling to the bottom and re-activating or replacing the license.  
     In BIG-IP Console -> Main -> System -> License.
       .. image:: ../images/Picture4.png

.. note:: 
   - IF the BIG-IP isn’t Activated then the lab will not work and be able to be completed.
   - Please wait 5 minutes after Activating to ensure data is flowing correctly to Kibana
