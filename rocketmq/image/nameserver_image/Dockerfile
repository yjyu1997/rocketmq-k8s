FROM www.yusora.top/library/jdk1.8:latest

RUN rm -f /etc/localtime \
&& ln -sv /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
&& echo "Asia/Shanghai" > /etc/timezone

ENV LANG en_US.UTF-8

ADD rocketmq-all-4.8.0-bin-release.tar.gz /usr/local/
RUN mv /usr/local/rocketmq-all-4.8.0-bin-release /usr/local/rocketmq-4.8.0
COPY namesrv.properties /usr/local/rocketmq-4.8.0/conf/

WORKDIR /usr/local/rocketmq-4.8.0
CMD ["/usr/local/rocketmq-4.8.0/bin/mqnamesrv","-c","/usr/local/rocketmq-4.8.0/conf/namesrv.properties"]

