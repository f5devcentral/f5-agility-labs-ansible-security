Kibana Dashboard
================

Using the Kibana Dashboard we can now see more information about our data exfiltration’s.  The data indicated on the dashboard indicates a breach of security and lost data, there could be one or two big green lines on the chart depending on the time between attacks above.

#. Finding an Abnormal file transferring in Kibana, The Single bar is an indication of a large data transfer

     .. image:: ../images/Attacks/Picture20.png
          :width: 850
#. Click on the large Green bar two or three times to examine it deeper and narrow the timeframe
     It will eventually narrow till you see one object on the map as RED and that should be North Korea
      
     .. image:: ../images/Attacks/Picture21.png
          :width: 850
#. In the Same window scroll down to the data fields you can get more data about the exfiltration and how its emulating an attack from North Korea and how data was exfiltrated.
     - In F5 Advanced WAF Alert Detail (last geoip.country_code2.keyword) - KP  
     - Network Flow Table (Total Transferred Octet Count) - 93MB
     - Layer 7 App Session Table – Type of Attack, Geo Location, and response codes

     .. image:: ../images/Attacks/Picture22.png
          :width: 850