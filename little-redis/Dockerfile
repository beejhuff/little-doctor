FROM centos:7
ENV http_proxy http://10.114.16.12:80
ENV https_proxy http://10.114.16.12:80
ENV HTTP_PROXY http://10.114.16.12:80
ENV HTTPS_PROXY http://10.114.16.12:80
ENV no_proxy "localhost,127.0.0.1,ge.com,3.0.0.0/8,10.0.0.0/8"

# install redis so we can gather number of clients
RUN yum install epel-release -y
RUN yum install redis -y
EXPOSE 6379
WORKDIR /tmp
ADD launch-redis.sh /tmp/
RUN ./launch-redis.sh
ENTRYPOINT ["/usr/bin/redis-server","/etc/redis.conf"]