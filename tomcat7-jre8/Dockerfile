FROM tomcat:7-jre8
ENV TZ=Asia/Shanghai
RUN echo $TZ > /etc/timezone
COPY ./Shanghai /etc/localtime
COPY ./Shanghai /usr/share/zoneinfo/Asia/Shanghai
COPY ./catalina.sh /usr/local/tomcat/bin
COPY ./context.xml /usr/local/tomcat/conf
COPY ./server.xml /usr/local/tomcat/conf
COPY ./*.jar /usr/local/tomcat/lib/
COPY ./fonts /usr/lib/jvm/java-8-openjdk-amd64/jre/lib/fonts

# 设置数据卷
RUN ln -s /nas/axinfu /root/
RUN ln -s /nas/upload /usr/local/tomcat/
RUN ln -s /nas/download /usr/local/tomcat/
RUN rm -rf /usr/local/tomcat/webapps && ln -s /nas/webapps /usr/local/tomcat/
RUN rm -rf /usr/local/tomcat/logs && ln -s /nas/logs /usr/local/tomcat/
WORKDIR /usr/local/tomcat/

