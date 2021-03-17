FROM www.yusora.top/library/jdk1.8:latest

RUN rm -f /etc/localtime \
&& ln -sv /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
&& echo "Asia/Shanghai" > /etc/timezone
 
ENV LANG en_US.UTF-8
ENV MAVEN_HOME /usr/local/maven
ENV PATH $PATH:$MAVEN_HOME/bin
 
ADD rocketmq-externals.tar.gz /usr/local
ADD apache-maven-3.3.9-bin.tar.gz /usr/local
RUN mv /usr/local/apache-maven-3.3.9 /usr/local/maven
 
WORKDIR /usr/local/rocketmq-externals/rocketmq-console/
RUN mvn clean package -Dmaven.test.skip=true
 
WORKDIR /usr/local/rocketmq-externals/rocketmq-console/target
EXPOSE 8080
CMD ["nohup","java","-jar","rocketmq-console-ng-1.0.0.jar","&"]
