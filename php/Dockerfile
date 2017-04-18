FROM centos:6

MAINTAINER Eric Poe <eric.poe@gmail.com>

# Set TERM environment var - so terminal cmds like `top` work
ENV TERM=xterm

RUN yum install -y wget epel-release
RUN wget http://rpms.famillecollet.com/enterprise/remi-release-6.rpm
RUN rpm -Uvh remi-release-6*.rpm
RUN yum update -y
RUN yum --enablerepo=remi-php71 install -y \
        php \
        php-pecl-apcu \
        php-gd \
        php-imap \
        php-intl \
        php-ldap \
        php-mbstring \
        php-mcrypt \
        php-mssql \
        php-mysqlnd \
        php-pecl-memcached \
        php-pecl-zip \
        php-xml \
        vim \
        && \
    yum clean all

WORKDIR /var/www/html

COPY php.ini /etc/php.ini