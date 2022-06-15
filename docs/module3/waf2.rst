Using Ansible Scripting to Modify WAF Policy
============================================

Ansible is an opensource IT automation engine that automates provisioning, configuration management, application deployment, orchestration and many other IT processes.  When used with Ansible Galaxy modules for F5 BIG-IP many modifications can be made to configure and/or deploy applications or services such as Web Application Firewall (WAF) policies.

#. In UDF -> Ansible Security Lab -> Components -> Ansible -> Access -> Web Shell

     .. image:: ../images/WAF/Picture4.png
#. Change directory to /git in Web Shell

     .. code-block::

       cd /git/sample-playbook

     .. image:: ../images/WAF/Picture5.png
#. Run the Ansible Playbook to change the WAF Policy to Blocking

     .. code-block::

       ansible-playbook awaf-blocking.yaml
      
     .. image:: ../images/WAF/Picture6.png
#. On the BIG-IP Validate that the enforcement mode changed from Transparent to Blocking (Refresh the page by clicking Policies List) Validate on the Notice that the WAF-Policy enforcement mode is “Transparent” this means it is not actively blocking any of the attacks however it is logging them.

     .. image:: ../images/WAF/Picture7.png
     .. image:: ../images/WAF/Picture8.png