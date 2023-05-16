# project1-
for the start I just made 3 serves: 1.for the app server. 2.for jankins server. 3.for my ansible server. for all the servers I download this:

webapp-(k8s cluster) -> (Docker+Minikube) 2.jankins-(jenkins). 3.ansible- (ansible+python+docker).
at the start I uplode a Dockerfile that contines:

'''Dockerfile
FROM centos:centos7 MAINTAINER ronc2000@hotmail.com RUN yum install -y httpd
zip
unzip ADD https://www.free-css.com/assets/files/free-css-templates/download/page254/photogenic.zip /var/www/html/ WORKDIR /var/www/html/ RUN unzip photogenic.zip RUN cp -rvf photogenic/* . RUN rm -rf photogenic photogenic.zip CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"] EXPOSE 80 22
'''

Here is a breakdown of the commands used in the Dockerfile: FROM centos:centos7: This line sets the base image for the container to the centos7 version of CentOS available on Docker Hub. MAINTAINER ronc2000@hotmail.com: This line sets the author's contact information for the image. RUN yum install -y httpd zip unzip: This command installs the Apache HTTP server and the zip and unzip utilities needed to extract the website files from the downloaded zip file. ADD https://www.free-css.com/assets/files/free-css-templates/download/page254/photogenic.zip /var/www/html/: This line downloads the photogenic.zip file from the specified URL and adds it to the container's /var/www/html/ directory. WORKDIR /var/www/html/: This command sets the working directory for subsequent commands to /var/www/html/. RUN unzip photogenic.zip: This command extracts the contents of the photogenic.zip file to the current directory. RUN cp -rvf photogenic/* .: This command copies the contents of the photogenic directory to the current directory, which is /var/www/html/. RUN rm -rf photogenic photogenic.zip: This command removes the photogenic directory and the photogenic.zip file. CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]: This line specifies the command to run when the container starts, which is to start the Apache HTTP server and keep it running in the foreground. EXPOSE 80 22: This line specifies that the container should listen on ports 80 and 22. Port 80 is used for HTTP traffic, while port 22 is used for SSH.
