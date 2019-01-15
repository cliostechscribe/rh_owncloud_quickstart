# Changing the Owncloud URL and import

By default, the URL http://<hostname>/owncloud (where <hostname is the name or IP address of the machine where Owncloud is installed) is used to access Owncloud, and Owncloud listens on the default web server port (port 80 for unsecure requests, port 443 for secure requests).  You may want to change  the URL so you can access Owncloud using direct requests to the server, and so you can use a different port.  

You make both changes by editing configuration files in the system.  

_NOTE_:  Remember to restart the web server after changing configuration files.  

## Changing the Owncloud URL

To change the Owncloud URL:

1. Modify the Owncloud configuration file `/etc/apache2/sites-enabled/owncloud.conf` using a simple text editor.  Update the `Alias` directive to alias the Owncloud directory to the web server root.  
  `Alias / "/var/www/owncloud/"`

2. Modify the Owncloud PHP configuration file `/var/www/owncloud/config/config.php` using a simple text editor.  Modify the parameter `overwrite.cli.url` to specify `localhost` or the IP address of the machine.  For example:  
  `'overwrite.cli.url' => 'http://localhost/',`  
  or  
  `'overwrite.cli.url' => 'http://10.10.10.129',`


## Changing the Owncloud port

Owncloud listens on the web server port (by default, port 80 for unsecure requrests, port 443 for secure requests).  If you want Owncloud to listen on a different port, you must configure the port for the web server.  
