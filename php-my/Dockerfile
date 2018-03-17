FROM php:7.2.3-fpm

RUN \
    apt-get update &&\
    apt-get upgrade -y &&\
    apt-get install -y git vim curl software-properties-common

# add this ppa
RUN add-apt-repository ppa:nilarimogard/webupd8
RUN apt-get update
# install launchpad-getkeys
RUN apt-get install launchpad-getkeys
# run it
RUN launchpad-getkeys
# php
# RUN apt-get install -y language-pack-en-base
RUN apt-get install -y locales locales-all
ENV LC_ALL en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US.UTF-8
RUN LC_ALL=en_US.UTF-8 add-apt-repository ppa:ondrej/php
RUN apt-get update
# Run apt-get install -y php7.2
RUN apt-get install -y php7.2 php7.2-fpm php7.2-cli php7.2-common php7.2-json php7.2-opcache php7.2-mysql php7.2-phpdbg php7.2-mbstring php7.2-gd php7.2-imap php7.2-ldap php7.2-pgsql php7.2-pspell php7.2-recode php7.2-soap php7.2-tidy php7.2-dev php7.2-intl php7.2-curl php7.2-zip php7.2-xml php-xdebug

COPY ./composer /usr/local/bin

COPY config/default /etc/nginx/sites-available
RUN rm -rf /etc/nginx/sites-enabled/default
RUN ln -s /etc/nginx/sites-available/default /etc/nginx/sites-enabled/