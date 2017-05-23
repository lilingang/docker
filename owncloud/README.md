# Owncloud

Docker image for [owncloud](https://owncloud.org/) based on image [owncloud](https://hub.docker.com/_/owncloud/)

# How to use this image
## SSL Certificate 
A certificate is required to use this image.
1. Create a new folder for the certificate
2. Make sure that the certificate file name is `chain.pem` and domain key is `domain.key`

## Start btsync
Starting the owncloud instance:
```
docker run -p 443:443 -v /path/to/certificate-folder:/ssl-cert --name owncloud -d lilg/owncloud
```
Then go to [https://youdomain.com/](https://youdomain.com) and go through the wizard

## Persistent data

 - `-v /<mydatalocation>/apps:/var/www/html/apps` installed / modified apps
 - `-v /<mydatalocation>/config:/var/www/html/config` local configuration
 - `-v /<mydatalocation>/data:/var/www/html/data` the actual data of your ownCloud

 Example
```
docker run \
--restart=always \
-p 443:443 \
-v /path/to/apps:/var/www/html/apps \
-v /path/to/config:/var/www/html/config \
-v /path/to/data:/var/www/html/data \
-v /path/to/certificate-folder:/ssl-cert \
--name owncloud \
-d lilg/owncloud
```
