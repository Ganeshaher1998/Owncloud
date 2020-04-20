# Owncloud
Using docker and docker-compose try to configure OwnCloud with OpenOffice

Installation And Configuration Of OwnCloud And Only Office Using Docker Compose :
prerequisites:
•	 CPU: dual core 2 GHz or better.
•	RAM: 2 GB or more
•	HDD: at least 50 GB of free space
•	At least 2 GB of swap
1: yum update:

2: installation of docker:


3. Disable SELINUX  by going in file /etc/sysconfig/selinux  and changing     enforcing  to disabled.

4: After this make the directory owncloud-docker-server  and go in that directory for further process.
      #mkdir owncloud-docker-server
      #cd /owncloud-docker-server

5:Installation of wget

6: Now  copy docker-compose.yml from GitHub repository by using wget command in that present directory.

7.Create An Environment  Configuration  File Now.
cat << EOF > .env
OWNCLOUD_VERSION=10.3
OWNCLOUD_DOMAIN=localhost
ADMIN_USERNAME=admin
ADMIN_PASSWORD=admin
HTTP_PORT=8080
EOF

8: Installation of docker compose by using following command: curl -L

9:And after installing it, give it appropriate permissions
# chmod +x /usr/local/bin/docker-compose
You can check version by using following command:
# docker-compose –version

10: Now Build And Start Container By Using Following Command.
 #Docker-compose  up  –d
11: Browse in your browser ‘localhost:8080’,  you  will observe  following  screen.
Login using the credentials provided in EOF file.


Configuration of ONLYOFFICE ON OWNCLOUD

11: INSTALL GIT PACKAGE IF YOU DON’T HAVE IT 


12; clone the onlyoffice’s repo in file docker-onlyoffice-ownclo
13. Now go in docker-onlyoffice-owncloud directory and again run docker compose command in that directory.


14: write set_configuration.sh script:

Vi set_configuration.sh

15: Run that script by command:

#git submodule update --remte

#bash set_configuration.sh command
16: then g
o to your browser and browse localhost in it, if everything is correct then you will be redirected to the same login page ,login using the same credentials.
After you login you will onlyoffice option as seen in the following scree 

17: if onlyoffice not enabled, 
click on admin in right corner and in that click on settings >Apps.
Check weather the onlyoffice is enabled or not,if not then click on disabled apps and find the onlyoffice and enable it. After enabling it you will see following output. 


