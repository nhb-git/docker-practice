# use base image
FROM ubuntu:china

# define maintainer
# MAINTAINER niu (niu@docker.com)
LABEL maintainer="niu@docker.com"

# install nginx, run nginx with no daemon
RUN apt-get update && \
    apt-get install -y nginx && \
    rm -rf /var/lib/apt/lists/* && \
    echo "\ndaemon off;" >> /etc/nginx/nginx.conf && \
    chown -R www-data:www-data /var/lib/nginx

# add script
ADD run.sh /run.sh
RUN chmod 755 /*.sh

# volume
VOLUME ["/etc/nginx/sites-enabled", "/etc/nginx/certs", "/etc/nginx/conf.d", "/var/log/nginx"]

# work dir
WORKDIR /etc/nginx

# cmd
CMD ["/run.sh"]

EXPOSE 80
EXPOSE 443