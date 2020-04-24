# README #


**What is this repository for?**

* Public IP address of many hosting servers are dynamic and it changes based on availability. Some examples include AWS EC2 instance, Home Servers, GCP Cloud, etc.
* This require updating the IP address in goDaddy DNS record so that requests are forwarded to correct IP address.
* This script uses cron jobs to check the current Public IP address of server and update the IP address in goDaddy Manage DNS. 
* Version: vZ.0 (Zero point O)
* OS: Linux. Tested on Ubuntu server 18.04 LTS with BASH shell.
* Prerequisite tools: curl, BASH shell.

**How do I get set up ?**

* Clone this repository in your server.
* Open godaddyDDNS/godaddyDDNS.properties file
* Update the properties values as below:

domain=domain.com
name=subdomainORwww
key=key-value-from-godaddy-developer-console
secret=secret-key-value-from-godaddy-developer-console

e.g. To update DNS Name *navi.example.com*

domain=example.com

name=navi

key=cvvgfvfd54jghgz8s

secret=dfgsx6daflx5]gkhhi8yjxf

* Key and Secret can be generated from godaddy Developer page. https://developer.godaddy.com/getstarted
* After updating. Run the script.
*./godaddyDDNS.sh*
* Check the log in godaddyDDNS.log file
* If log status is OK. Its workinf fine. Verify the DNS record in godaddy account.
* Create a crontab entry to run the godaddyDDNS.sh file every five minutes.
* Youtube video to be released soon. Link will be updated here.

**NOTES:**
goDaddy supports 60 requests per minutes. This scripts uses 2 requests. So, Make sure to create cronjob accordingly so that request doesn't exceed 60 request per minute or else it will fail.


**Contribution guidelines**

* You can create issue here --> https://github.com/navilg/godaddyDDNS/issues 

**How to reach me ?**

* Repo owner or admin: Navratan Gupta <navilg0409@gmail.com>
* You can reach out to me on navilg0409@gmail.com for any feedback.

**Special mention to https://github.com/markafox/GoDaddy_Powershell_DDNS which is base for this script.**

