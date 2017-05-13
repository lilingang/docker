FROM owncloud
MAINTAINER lilg <lilg@asiainfo.com>

#chain.pem
#domain.key
RUN mkdir /ssl-cert
RUN ln -s /etc/apache2/sites-enabled/000-default-ssl.conf /etc/apache2/sites-available/default-ssl.conf
ADD default-ssl.conf /etc/apache2/sites-available/default-ssl.conf

EXPOSE 443

ENTRYPOINT ["/entrypoint.sh"]
CMD ["apache2-foreground"]
