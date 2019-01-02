## DEMO WEBSERVER
# Base operating system image based on centos 7 
FROM	centos:7

# Enviornment variable
ENV TERM=xterm


# Copying Index file
COPY	index.html /var/www/html/index.html

# Package installation and configuration changes
RUN 	yum install -y httpd && yum clean all -y && \
    	sed -i 's/Listen 80/Listen 8080/' /etc/httpd/conf/httpd.conf && \
        useradd web -u 1001 && \
	echo web:redhat | chpasswd && \
    	chmod -R a+rwx /run/httpd /etc/httpd/logs

# Listen on below port
EXPOSE 8080

# User 
USER 1001

# Always execute entry point
ENTRYPOINT	["/usr/sbin/httpd"]

# Run process in foregroud as a parameter
CMD		["-DFOREGROUND"] 
