#FROM amazonlinux

#RUN yum -y update
#RUN yum -y install httpd
#RUN yum -y install php

#COPY ./index.php /var/www/html/index.php

#CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]

#EXPOSE 80
FROM ubuntu:latest

# Update the package list and install Apache and PHP
RUN apt-get update && \
    apt-get install -y apache2 php && \
    echo "ServerName localhost" >> /etc/apache2/apache2.conf && \
    apt-get clean

# Copy the PHP file to the web server's root directory
COPY ./index.php /var/www/html/index.php

# Expose port 80
EXPOSE 80

# Start Apache HTTP Server in the foreground
CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
