FROM centos:7

# Set TERM environment var - so terminal cmds like `top` work
ENV TERM=xterm

RUN yum install -y epel-release \
        http://rpms.famillecollet.com/enterprise/remi-release-7.rpm \
        http://repo.okay.com.mx/centos/7/x86_64/release/okay-release-1-1.noarch.rpm \
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
