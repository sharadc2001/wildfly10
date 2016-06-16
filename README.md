# wildfly10
wildfly10 with keycloak server with SSL 


This will will build wildfly10 image with Bluemix default Image
----------------------------------------------------------------
To get started setup Bluemix client environment to get connected to Bluemix

Option#1 : Cloud Foundry and IBM Container Plugins
--------------------------------------------------

1. Install Cloud Foundry
  Download latest installer cf from the link and run the below command
  https://github.com/cloudfoundry/cli/releases   
  sudo dpkg -i cf-cli-installer_6.18.0_x86-64.deb
  
  Run cf -v to verify the cloud foundry version and its installation

2. Installing IBM Container Plugins
   cf install-plugin https://static-ice.ng.bluemix.net/ibm-containers-linux_x64
   Run cf plugins to verify plugin installation
Examples:
-------------
  sudo cf login -a https://api.ng.bluemix.net
  Username>
  Password>
  ORG>
  sudo cf ic login
  sudo cf ic pull registry.ng.bluemix.net/ibmnode:latest  
   
Option#2:Another Quick option available is setting up Bluemix command   
-----------------------------------------------------------------------	 
https://console.ng.bluemix.net/docs/cli/reference/bluemix_cli/index.html
download bluemix command from the above url and follow the steps for Installation.
Syntax will be as follows:

Examples:
-----------
sudo bluemix login -a https://api.ng.bluemix.net
Username>
Password>
ORG>
sudo bluemix ic init
sudo bluemix ic pull registry.ng.bluemix.net/ibmnode:latest

Building docker image from docker file
----------------------------------------

sudo docker build -t="jboss/wildfly10"

Running Docker Image
----------------------
sudo docker run -it -p 8080:8080 -p 8443:8443 -p 9993:9993 -p 9990:9990 jboss/wildfly10 /opt/wildfly/bin/standalone.sh -b 0.0.0.0 -bmanagement 0.0.0.0

Wildfly Console URL
---------------------

http://<hostIP>:8080/console

Keycloak URL
----------------
https://<hostIP>:8443/auth