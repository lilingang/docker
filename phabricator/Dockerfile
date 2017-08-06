FROM picoded/phabricator
MAINTAINER lilg <lingang.li@ifudata.com>

#安装svn
RUN apt-get update && apt-get install -y subversion php5-apcu

#安装php-apcu
#RUN pecl install apcu && docker-php-ext-enable apcu

RUN mkdir -p /repo

ADD append.script /append.script

RUN sed -i '/echo "## Applying MySQL configurations - ${MYSQL_HOST}";/r /append.script' setup-and-run.sh

RUN rm -rf /append.script

EXPOSE 22 80
ENTRYPOINT ./setup-and-run.sh && apache2-foreground
CMD ./setup-and-run.sh && apache2-foreground
