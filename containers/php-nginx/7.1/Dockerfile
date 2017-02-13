FROM ubuntu

MAINTAINER Ronaldo Meneguite <ronaldo@fireguard.com.br>

ENV DEBIAN_FRONTEND=noninteractive

#    apt-add-repository ppa:git-core/ppa -y && \
RUN echo "---> Update Source Repository" && \
    apt-get update && \
    apt-get install -y language-pack-en-base && \
    export LC_ALL=en_US.UTF-8 && \
    export LANG=en_US.UTF-8 && \
    apt-get install software-properties-common -y && \
    add-apt-repository ppa:ondrej/php -y && \
    add-apt-repository ppa:nginx/stable -y && \
    apt-get update && \
    apt-get upgrade -y  && \

    echo "---> Install utils" && \
    apt-get install -y apt-transport-https curl libxrender1 libfontconfig1 libxext6 wget nano  && \

    echo "---> Install PHP 7.1 and your modules" && \
    apt-get -y install php7.1 php7.1-cli php7.1-bz2 php7.1-curl php7.1-fpm php7.1-gd php7.1-imagick php7.1-imap \
        php7.1-intl php7.1-json php7.1-mbstring php7.1-mcrypt php7.1-mysql php7.1-opcache php7.1-redis php7.1-sqlite3 \
        php7.1-xdebug php7.1-xml php7.1-zip php7.1-phpdbg php7.1-mongodb php7.1-pgsql php7.1-soap && \

    echo "---> Installing Composer" && \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \

    echo "---> Install Git and Git Flow" && \
    apt-get install git git-flow -y && \
    git config --global user.email "${GIT_EMAIL}" && \
    git config --global user.name "${GIT_USER_NAME}" && \

    echo "---> Installing NGINX" && apt-get install -y nginx && \

    echo "---> Cleaning up" && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

COPY nginx.conf /etc/nginx/nginx.conf 

## APPICATION DIRECTORY
WORKDIR "/project"

# Define default command.
CMD service php7.1-fpm start && nginx

# EXPOSE PORTS.
EXPOSE 80