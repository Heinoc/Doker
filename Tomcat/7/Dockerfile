FROM heinoc/java:1.8

MAINTAINER heinoc <tracychsh@126.com>


RUN set -eux \
	&& cd /home/work/temp \
# -----------------------------------------------------------------------------
# 下载安装包
# -----------------------------------------------------------------------------
	&& wget -O tomcat7.tar.gz "https://mirrors.tuna.tsinghua.edu.cn/apache/tomcat/tomcat-7/v7.0.82/bin/apache-tomcat-7.0.82.tar.gz" \
	&& tar -C /home/work/app -xzf tomcat7.tar.gz \
# -----------------------------------------------------------------------------
# 删除安装包
# -----------------------------------------------------------------------------
	&& rm -rf /home/work/temp/*


# -----------------------------------------------------------------------------
# 修改 tomcat-users.xml 配置文件，启用admin用户
# -----------------------------------------------------------------------------
ADD conf/tomcat-users.xml /home/work/app/apache-tomcat-7.0.82/conf/tomcat-users.xml


# -----------------------------------------------------------------------------
# 配置tomcat环境变量
# -----------------------------------------------------------------------------
ENV CATALINA_HOME   /home/work/app/apache-tomcat-7.0.82


EXPOSE 8080


CMD ["/home/work/app/apache-tomcat-7.0.82/bin/catalina.sh", "run"]