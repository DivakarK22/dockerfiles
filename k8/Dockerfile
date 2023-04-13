FROM centos:latest

COPY sensu.repo /etc/yum.repos.d/

RUN cd /etc/yum.repos.d/
RUN sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-*
RUN sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-*
# RUN yum update -y 
RUN yum install git -y
RUN cd /
RUN git clone https://github.com/DivakarK22/scripts.git
RUN pwd
RUN ls
RUN cd /scripts/setups/
RUN cp /scripts/setups/node_exporter.sh /
RUN bash node_exporter.sh

CMD systemctl start node_exporter