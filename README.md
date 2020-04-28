# Owncloud



Checkout Output on LinkedIn : https://www.linkedin.com/posts/ganesh-m-aher-323644157_righteducation-docker-vimaldaga-activity-6659652169819656192-Ed20



Using docker and docker-compose try to configure OwnCloud with OnlyOffice.

What is OwnCloud?
OwnCloud is open-source software, that allows you to run a personal cloud file storage service. It has features that are comparable to other cloud storage services such as Dropbox.
The OwnCloud server software can be installed free of charge on Linux, and the client software can be installed on computers running Windows, OS X, or Linux. Mobile apps are also available for Android and iOS.

What is OnlyOffice?
ONLYOFFICE Document Server is a free collaborative online office suite comprising viewers and editors for texts, spreadsheets and presentations, fully compatible with Office Open XML formats: .docx, .xlsx, .pptx and enabling collaborative editing in real time.
ONLYOFFICE Document Server contains the following components:
•	server - the backend server software layer which is the base for all other components of ONLYOFFICE Document Server.
•	core - server core components of ONLYOFFICE Document Server which enable the conversion between the most popular office document formats (DOC, DOCX, ODT, RTF, TXT, PDF, HTML, EPUB, XPS, DjVu, XLS, XLSX, ODS, CSV, PPT, PPTX, ODP).
•	sdkjs - JavaScript SDK for the ONLYOFFICE Document Server which contains API for all the included components client-side interaction.
•	web-apps - the frontend for ONLYOFFICE Document Server which builds the program interface and allows the user to create, edit, save and export text, spreadsheet and presentation documents using the common interface of a document editor.
•	dictionaries - dictionaries of various languages used for spell checking in ONLYOFFICE Document Server.
•	sdkjs-plugins - the add-ons for ONLYOFFICE Document Server used for the developers to add specific functions to the editors which are not directly related to the OOXML format.

What Is Docker Compose?
Docker Compose is used to run multiple containers as a single service. For example, suppose you had an application which required NGINX and MySQL, you could create one file which would start both the containers as a service without the need to start each one separately.
With Compose, you use a YAML file to configure your application’s services. Then, with a single command, you create and start all the services from your configuration and it will work in all environments for example: production, staging, development, testing, as well as CI workflows.  
Using Compose is basically a three-step process:
1.	Define your app’s environment with a Dockerfile so it can be reproduced anywhere.


2.	Define the services that make up your app in docker-compose.yml so they can be run together in an isolated environment.


3.	Run docker-compose up and Compose starts and runs your entire app.


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


