FROM centos:6

LABEL maintainer="eric.poe@gmail.com"

# Set TERM environment var - so terminal cmds like `top` work
ENV TERM=xterm

RUN find /etc/yum.repos.d/*.repo | xargs -i sed -i 's/mirror\.centos\.org\/centos/vault.centos.org/g;s/$releasever/6.10/g;s/mirrorlist/#mirrorlist/g;s/#baseurl/baseurl/g;s/download\.fedoraproject\.org\/pub\/epel/archives.fedoraproject.org\/pub\/archive\/epel/g' {} \
    && yum install -y epel-release \
        http://rpms.famillecollet.com/enterprise/remi-release-6.rpm \
        http://repo.okay.com.mx/centos/6/x86_64/release/okay-release-1-1.noarch.rpm \
        && \
    yum clean all

RUN yum update -y \
    && yum --enablerepo=remi-php71 install -y \
        git \
        php \
        php-bcmath \
        php-gd \
        php-imap \
        php-intl \
        php-ldap \
        php-mbstring \
        php-mcrypt \
        php-mssql \
        php-mysqlnd \
        php-opcache \
        php-pecl-apcu \
        php-pecl-memcached \
        php-pecl-zip \
        php-xml \
        vim \
        && \
    yum clean all

WORKDIR /var/www/html

COPY php.ini /etc/php.ini
