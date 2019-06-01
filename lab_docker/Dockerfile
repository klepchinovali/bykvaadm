FROM debian
RUN apt-get update && apt-get -y upgrade && apt -y install nginx && apt-get clean && \
    cd /var/www/ && rm -rf ./* && \
    mkdir -p klepchinovali.com/img && \
    chmod -R 754 /var/www/klepchinovali.com/ && \
    useradd Elizaveta && groupadd Klepchinova && usermod -aG Klepchinova Elizaveta && \
    chown -R Elizaveta:Klepchinova /var/www/klepchinovali.com/ && \
    sed -i 's/\/var\/www\/html/\/var\/www\/klepchinovali.com/g' /etc/nginx/sites-enabled/default && \
    sed -i 's/user www-data/user Elizaveta/g' /etc/nginx/nginx.conf
ADD index.html /var/www/klepchinovali.com/
ADD img.jpg /var/www/klepchinovali.com/img/
CMD ["nginx", "-g", "daemon off;"]
