# Tomcat7 JMX Monitoring

## Resources
* [Enabling JMX Remote](http://tomcat.apache.org/tomcat-7.0-doc/monitoring.html#Enabling_JMX_Remote)
* [Remote Lifecycle Listener](http://tomcat.apache.org/tomcat-7.0-doc/config/listeners.html#JMX_Remote_Lifecycle_Listener_-_org.apache.catalina.mbeans.JmxRemoteLifecycleListener)

## Modifications

### $CATALINA_BASE/bin/catalina.sh
* Add JAVA_OPTS
* Add CATALINA_OPTS

### $CATALINA_BASE/conf
* Add jmxremote.access
* Add jmxremote.password
* Add JmxRemoteLifecycleListener in server.xml

