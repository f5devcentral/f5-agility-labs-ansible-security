Validate that WAF is now Blocking injection Attacks
===================================================

After modifying the WAF policy from transparent to blocking the F5 BIG-IP should now be enforcing its protections, specifically to block injection attacks.  This next section will show that the commands previously used will not be accessible anymore as the F5’s WAF Policy has the ability to detect and prevent these types of attacks.

#. In the DVWA Website in the XRDP Session (if has gateway timeout click back on the browser) to get to the Command Injection Screen

     .. image:: ../images/WAF/Picture8.png
          :width: 850
#. Re-Run the first injection command to now see that the F5 BIG-IP WAF is blocking the Injection attempt.
     In the DVWA Website in the XRDP Session
     .. code-block::

       8.8.8.8 | cat /etc/password

     .. image:: ../images/WAF/Picture9.png
          :width: 850
#. Re-Enable Transparent WAF Policy via Ansible Script **(Needed for Next Section)**
     In the Ansible Shell

     .. code-block::

       ansible-playbook awaf-transparent.yaml
      
     .. image:: ../images/WAF/Picture10.png
          :width: 850