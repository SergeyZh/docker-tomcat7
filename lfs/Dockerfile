FROM sergeyzh/tomcat7-log4j:amazoncorretto8

MAINTAINER Sergey Zhukov, sergey@jetbrains.com

ENV LFS_VER 4.2.4

RUN wget -O /home/tomcat/apache-tomcat-current/lib/lfsappenders-${LFS_VER}.jar https://s3.amazonaws.com/logfaces/v424/lfsappenders-${LFS_VER}.jar
ADD lfs-config.sh /root/prerun/

# Apply additional transformations to children images
ONBUILD ADD wrapper /home/tomcat/wrapper/
ONBUILD ADD xslt /home/tomcat/xslt/
ONBUILD ADD cacerts /home/tomcat/cacerts/
ONBUILD RUN bash -c ". /apply.sh"

