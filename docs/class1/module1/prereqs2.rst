Validate Lab Functionality
==========================

License F5
********** 
Ensure that the F5 is licensed, login to the F5 

#. Access BIG-IP through UDF Lab
     In UDF -> Ansible Security Lab -> Components -> BIGIP-WAF -> Access -> TMUI
       .. image:: ../images/Prereqs/Picture2.png
#. Login to BIG-IP Webpage
     -  Username: admin
     -  Password: admin123

       .. image:: ../images/Prereqs/Picture3.png
#. Ensure that the BIG-IP Is licensed, if it is you should see that its Online and Active, if its marked Offline with RED and doesn’t change or has a message about licensing being bad, you can try scrolling to the bottom and re-activating or replacing the license.  
     In BIG-IP Console -> Main -> System -> License.
       .. image:: ../images/Prereqs/Picture4.png

.. note:: 
   - IF the BIG-IP isn’t Activated then the lab will not work and be able to be completed.
   - Please wait 5 minutes after Activating to ensure data is flowing correctly to Kibana
