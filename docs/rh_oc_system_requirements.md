# Owncloud system requirements

Before you begin, make sure your system matches the requirements for Owncloud installation.

## Memory requirements

The official minimum RAM to run Owncloud is 128MB.  The recommended minimum is 512 MB.

## Required operating system configurations

Make sure the user used to install Owncloud has privileges to run sudo.

## Required supporting software
Owncloud requires the following software:

* Web server:  Apache 2.4  
For details about checking the status of the Apache web server in RedHat Enterprise Linux 7.x, see [https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/system_administrators_guide/ch-web_servers](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/system_administrators_guide/ch-web_servers).

* Database:  Maria 5.5 or later  (NOTE:  Maria supercedes MySQL in Red Hat.)
For details about checking the status of the MariaDB server in Red Hat Enterprise Linux 7.1, see [https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/selinux_users_and_administrators_guide/chap-managing_confined_services-mariadb](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/selinux_users_and_administrators_guide/chap-managing_confined_services-mariadb).

* PHP:  PHP Runtime 7.2
  *To check whether PHP is installed and the current version, in the directory ``/var/www/html/``, create a file named ``test.php``.  Include the following code  
    `<?php phpinfo(); ?>`  
Start a browser and enter http://<your-web-server>/test.php in the address field.  If PHP is installed and properly configured, the system returns a PHP information page, including the PHP version.
 *  If PHP is not installed:
   1. Run the following commands to enable the Red Hat Solftware Collection repositories that include the PHP packages:  
    sudo subscription-manager repos --enable rhel-7-server-extras-rpms
    sudo subscription-manager repos --enable rhel-7-server-optional-rpms
    sudo subscription-manager repos --enable rhel-server-rhscl-7-rpms

  2. Update the software packages.  Run the command `sudo yum update`.
  3. Install PHP.  Run the command  `sudo yum install rh-php72`.
