# Installing Owncloud on your machine

## Before you begin

Before you begin installation, make sure your system meets all requirements.  See [Owncloud system requirements](rh_oc_system_requirements.html).

## Installing Owncloud

1. Enable the Owncloud repositories.  Run the command `sudo rpm --import https://download.owncloud.org/download/repositories/production/RHEL_7/repodata/repomd.xml.key`.
2. Install Owncloud code to your machine.  Run the following commands:  
    `sudo wget http://download.owncloud.org/download/repositories/production/RHEL_7/ce:stable.repo -O /etc/yum.repos.d/ce:stable.repo
    sudo yum clean all
    sudo yum install owncloud-files`
3. Create a database and user for Owncloud.  
  1. Log in to MariaDB as root.  Run the command `mysql -u root -p <password>`, where <password> is the root user's password.
  2. Create the database.  At the MySQL prompt, run the command ` CREATE DATABASE owncloud;`.
  3. Grant the Owncloud user to the database.  At the MySQL prompt, run the command `GRANT ALL ON owncloud.* to 'owncloud'@'localhost' IDENTIFIED BY '_password_';`.
  4. Enable the Owncloud user privileges.  At the MySQL prompt, run the command ` FLUSH PRIVILEGES;`.
  5. Exit the database prompt.  Run the command `quit`.
4. Run the Owncloud web installer.  Start a browser and in the address field, enter *http://&lt;hostname&gt;/owncloud*, where &lt;hostname&gt; is the name or IP address of the machine where you are installing Owncloud.  
The system returns the Owncloud Create and admin account page.
5. The admin user name defaults to "admin".  You can change the admin user name to a name you prefer.  Enter a _password_ for the admin user.  
6. Scroll down the page and enter the database credentials.  
7. Click _Finish setup_.  
Owncloud completes the setup process.  When setup is complete, Owncloud displays the admin dashboard.
