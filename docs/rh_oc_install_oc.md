# Installing Owncloud on your machine

## Before you begin

Before you begin installation, make sure your system meets all requirements.  See [Owncloud system requirements](rh_oc_system_requirements.html).

## Installing Owncloud

1. Enable the Owncloud repositories.  Run the command `sudo rpm --import https://download.owncloud.org/download/repositories/production/RHEL_7/repodata/repomd.xml.key`.
2. Install Owncloud code to your machine.  Run the following commands:  
    sudo wget http://download.owncloud.org/download/repositories/production/RHEL_7/ce:stable.repo -O /etc/yum.repos.d/ce:stable.repo
    sudo yum clean all
    sudo yum install owncloud-files
3. Run the Owncloud web installer.  Start a browser and in the address field, enter http://<hostname>/owncloud, where <hostname> is the name or IP adderss of the machine where you are installing Owncloud.  
