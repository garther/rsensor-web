# Rsensor - web node
**We are totally in Work In Progress  mode ;)**
# Components
* Debian 9
* Apache Httpd
* Python 3
* Redis
# Assumptions
Below how-to assumes you already have a domain name and DNS configured pointing to your server.
# Installation
## Web Server with SSL
### Install Apache Httpd
```
apt install -y apache2
```
### Install Certbot, the Let's Encrypt Client
If you have own SSL certificate, skip this step...
```
# apt install -y python-certbot-apache
```
Generate certificate for your domain.
```
# export mydomain="mysensor.rsensor.pl"
# certbot --authenticator standalone --installer apache -d ${mydomain} --pre-hook "systemctl stop apache2" --post-hook "systemctl start apache2"
```
After everything is succesfull, you should see a question regarding HTTPS access is required or optional. I suggest to use the second option and have always enebled secure communication.

# Credits:
Based on project:
https://www.rigacci.org/wiki/doku.php/doc/appunti/hardware/raspberrypi_air
