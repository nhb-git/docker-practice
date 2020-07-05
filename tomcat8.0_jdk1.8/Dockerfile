# use base image
FROM ubuntu:china

# user info
LABEL maintainer="docker@user.com"

# setting env
ENV DEBIAN_FRONTEND="noninteractive"

# install tomcat's software
# RUN apt-get install -yq --no-install-recommends wget pwgen ca-certificates && \
#     apt-get clean && \
#     rm -rf /var/lib/apt/lists/*

ENV CATALINA_HOME='/tomcat'
ENV JAVA_HOME='/jdk'

ADD apache-tomcat-8.5.56 /tomcat
ADD jdk1.8.0_251 /jdk

# ADD create_tomcat_admin_user.sh /create_tomcat_admin_user.sh
ADD run.sh /run.sh
RUN chmod +x /*.sh
RUN chmod +x /tomcat/bin/*.sh

EXPOSE 8080
CMD ["/run.sh"]