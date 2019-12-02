readme
报错Cannot find /home/jarries/apache-tomcat-8.5.38/bin/setclasspath.sh

解决方案：
1.设置环境变量
export JAVA_HOME_8=/usr/bin/java/jdk1.8.0_211
export JRE_HOME_8=/usr/bin/java/jdk1.8.0_211/jre
export CATALINA_BASE_8=/home/jarries/apache-tomcat-9.0.16
export CATALINA_HOME_8=/home/jarries/apache-tomcat-9.0.16
export CLASSPATH_8=.:${CATALINA_HOME_8}/bin/tomcat-juli.jar:${CATALINA_HOME_8}/bin/bootstrap.jar:$JAVA_HOME_8/lib:$JAVA_HOME_8/lib/tools.jar:$JAVA_HOME_8/jre/lib
export PATH_8=$JAVA_HOME_8/bin:$JRE_HOME_8/bin:$PATH

2.在bin/catalina.sh中第一句有效代码前面插入
export JAVA_HOME=$JAVA_HOME_8
export JRE_HOME=$JRE_HOME_8
export CATALINA_BASE=$CATALINA_BASE_8
export CATALINA_HOME=$CATALINA_HOME_8
export CLASSPATH=$CLASSPATH_8
export PATH=$PATH_8

source /etc/profile