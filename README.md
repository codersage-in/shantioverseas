# shantioverseas

Command to Restart httpd on system reboot : sudo chkconfig httpd on

Directory location: /var/www/html

sudo yum install mod_ssl

run sudo service httpd restart

First, copy your certificate files to the directory where you keep your certificate and key files. Typically, this directory is /etc/ssl/ for your certificate.crt and ca_bundle.crt files, and /etc/ssl/private/ for your private.key file.

run sudo service httpd restart

Locate configuration file : /etc/httpd/conf.d/ssl.conf

Configure Virtual Host by chaning following parameteres in the file:

SSLCertificateFile       /etc/ssl/certificate.crt
SSLCertificateKeyFile    /etc/ssl/private/private.key
SSLCertificateChainFile  /etc/ssl/ca_bundle.crt

run sudo service httpd restart

To redirect the port 80 to 443 add followng to virtual host file (ssl.conf)

<VirtualHost *:80>
ServerName shantioverseas.com.sg
   Redirect permanent / https://shantioverseas.com.sg/
</VirtualHost>
