F5 BIG-IP Web Application Firewall
==================================

F5 Advanced WAF employs countermeasures to detect and stop evolving application layer threats. At a high level, Advanced WAF integrates behavioral analysis and dynamic code injections as its two main mechanisms available to more completely assess the threat associated with any given client session.

#. In UDF -> Ansible Security Lab -> Components -> BIGIP-WAF -> Access -> TMUI
     - username: admin
     - password: admin123

     .. image:: ../images/WAF/Picture1.png
#. In the Main Menus -> Security -> Click on Application Security
      
     .. image:: ../images/WAF/Picture2.png
#. Notice that the WAF-Policy enforcement mode is “Transparent” this means it is not actively blocking any of the attacks however it is logging them.
      
     .. image:: ../images/WAF/Picture3.png