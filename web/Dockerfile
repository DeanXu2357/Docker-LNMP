FROM ubuntu:latest

RUN \
    apt-get update &&\
    apt-get upgrade -y &&\
    apt-get install -y nginx git vim curl

RUN apt-get -y install software-properties-common
# RUN add-apt-repository ppa:ondrej/php

# RUN apt-get install -y nginx php7.2 php7.2-fpm php7.2-cli php7.2-common php7.2-json php7.2-opcache php7.2-mysql php7.2-phpdbg php7.2-mbstring php7.2-gd php7.2-imap php7.2-ldap php7.2-pgsql php7.2-pspell php7.2-recode php7.2-soap php7.2-tidy php7.2-dev php7.2-intl php7.2-curl php7.2-zip php7.2-xml php-xdebug


# php
RUN apt-get install -y language-pack-en-base
RUN LC_ALL=en_US.UTF-8 add-apt-repository ppa:ondrej/php
RUN apt-get update
# Run apt-get install -y php7.2
RUN apt-get install -y php7.2 php7.2-fpm php7.2-cli php7.2-common php7.2-json php7.2-opcache php7.2-mysql php7.2-phpdbg php7.2-mbstring php7.2-gd php7.2-imap php7.2-ldap php7.2-pgsql php7.2-pspell php7.2-recode php7.2-soap php7.2-tidy php7.2-dev php7.2-intl php7.2-curl php7.2-zip php7.2-xml php-xdebug

# Composer
# RUN \
#     curl -sS https://getcomposer.org/installer | php && \
#     mv composer.phar /usr/local/bin/composer && \
#     composer self-update
COPY config/composer /usr/local/bin

COPY config/default /etc/nginx/sites-available
RUN rm -rf /etc/nginx/sites-enabled/default
RUN ln -s /etc/nginx/sites-available/default /etc/nginx/sites-enabled/

# RUN service nginx start
CMD ["nginx", "-g", "daemon off;"]


# VOLUME ["/var/www/html", "/var/log", "/etc/nginx", "/etc/php"]

EXPOSE 80
