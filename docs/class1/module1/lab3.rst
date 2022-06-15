Validate Lab Functionality
==========================

Verify Kibana
*************
Kibana is a free and open frontend application that sits on top of the Elastic Stack, providing search and data visualization capabilities for data indexed in Elasticsearch. Kibana also acts as the user interface for monitoring, managing, and securing an Elastic Stack cluster — as well as the centralized hub for built-in solutions developed on the Elastic Stack.

#. Access Kibana through UDF Lab (Node 1)
     In UDF -> Ansible Security Lab -> Components -> Node 1 -> Access -> Kibana
       .. image:: ../images/Picture5.png
#. Login to Kibana Webpage
     -  Username: elastic
     -  Password: password

       .. image:: ../images/Picture6.png
#. Check the Kibana Dashboard  
       .. image:: ../images/Picture7.png
#. If working correctly should see something similar to below (if Source IP addresses is 0 check BIG-IP License)  
       .. image:: ../images/Picture8.png
        

.. note:: 
   - IF the BIG-IP isn’t Activated then the lab will not work and be able to be completed.
   - Please wait 5 minutes after Activating to ensure data is flowing correctly to Kibana