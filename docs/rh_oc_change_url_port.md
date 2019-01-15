# Changing the Owncloud URL and import

By default, the URL http://<hostname>/owncloud (where <hostname> is the name or IP address of the machine where Owncloud is installed) is used to access Owncloud, and Owncloud listens on the default web server port (port 80 for unsecure requests, port 443 for secure requests).  You may want to change  the URL so you can access Owncloud using direct requests to the server, and so you can use a different port.  

You make both changes by editing configuration files in the system.  

_NOTE_:  Remember to restart the web server after changing configuration files.  

## Changing the Owncloud URL

To change the Owncloud URL:

1. Modify the Owncloud configuration file `/etc/apache2/sites-enabled/owncloud.conf` using a simple text editor.  Update the `Alias` directive to alias the Owncloud directory to the web server root.  
  `Alias / "/var/www/owncloud/"`

2. Save the file.

3. Modify the Owncloud PHP configuration file `/var/www/owncloud/config/config.php` using a simple text editor.  Modify the parameter `overwrite.cli.url` to specify `localhost` or the IP address of the machine.  For example:  
  `'overwrite.cli.url' => 'http://localhost/',`  
  or  
  `'overwrite.cli.url' => 'http://10.10.10.129',`

4. Save the file.

5.  Restart the Apache web server.

In the first example, requests to http://localhost immediately return Owncloud.  In the second examples, requests to http://10.10.10.129 immediately return Owncloud.


## Changing the Owncloud port

Owncloud listens on the web server port (by default, port 80 for unsecure requrests, port 443 for secure requests).  If you want Owncloud to listen on a different port, you must configure the port for the web server.

To change the web server port on Apache:

1.  Open the file `/etc/apache2/ports.conf` using a simple text editor.  

2. Modify the Listen directive to specify the new port.  For example, if you want to specify port 8080, you would change the Listen directive to  
`Listen 8080`

3. Save the file.

4. Open the file `/etc/apache2/sites-enabled/000-default.conf`using a simple text editor.  

5. Modify the virtual host directive to specify the new port.  Continuing the port 8080 example., the new directive would be:  
`<VirtualHost *: 8080>`

6. Save the file.

7. Restart the web server.  

After these edits, all requests to the server must specify port 8080.  For example:  

  `http://10.10.10.129:8080`
