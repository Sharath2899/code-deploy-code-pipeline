# code-deploy-code-pipeline
Open and deploy the dev.server in putty with the following steps : 

Sample HTML code.
-----------------
<html>
<h2> Sample App Version 1 </h2>
</html>

Create appspec.yml
------------------
version: 0.0
os: linux
files:
 - source: /index.html
   destination: /var/www/html/
hooks:
 BeforeInstall:
  - location: scripts/httpd_install.sh
    timeout: 300
    runas: root
  - location: scripts/httpd_start.sh
    timeout: 300
    runas: root
ApplicationStop:
  - location: scripts/httpd_stop.sh
    timeout: 300
    runas: root
----------***__---------**___-------
mkdir scripts
cd scripts
vi httpd_install.sh
vi httpd_start.sh
vi httpd_stop.sh
