## Tomcat7 JMX Monitoring

### Resources
* [Enabling JMX Remote](http://tomcat.apache.org/tomcat-7.0-doc/monitoring.html#Enabling_JMX_Remote)
* [Remote Lifecycle Listener](http://tomcat.apache.org/tomcat-7.0-doc/config/listeners.html#JMX_Remote_Lifecycle_Listener_-_org.apache.catalina.mbeans.JmxRemoteLifecycleListener)

### Modifications

#### $CATALINA_BASE/bin/catalina.sh

* Add CATALINA_OPTS
```bash
# set variables for remote jmx
CATALINA_OPTS="-Dcom.sun.management.jmxremote \
-Dcom.sun.management.jmxremote.ssl=false \
-Dcom.sun.management.jmxremote.authenticate=true \
-Dcom.sun.management.jmxremote.password.file=/Library/Tomcat7/conf/jmxremote.password \
-Dcom.sun.management.jmxremote.access.file=/Library/Tomcat7/conf/jmxremote.access"
```

#### $CATALINA_BASE/conf

* Add jmxremote.access, access authorization (username, authorization)
```bash
admin readonly
admin readwrite
```

* Add jmxremote.password, password file (username, password)
```bash
admin tomcat
admin tomcat
```

* Download [JMX Remote jar](http://apache.sunsite.ualberta.ca/tomcat/tomcat-7/v7.0.61/bin/extras/catalina-jmx-remote.jar) and copy to $CATALINA_BASE/lib

* Add JmxRemoteLifecycleListener in server.xml
```bash
  <!-- Remote JMX Listener -->
  <!-- Connnection: service:jmx:rmi://localhost:8084/jndi/rmi://localhost:8083/jmxrmi -->
  <Listener className="org.apache.catalina.mbeans.JmxRemoteLifecycleListener" 
    rmiRegistryPortPlatform="8083" rmiServerPortPlatform="8084" />
```

* Restart Tomcat.

* [Download and install VistualVM](https://visualvm.java.net/download.html)

* Start VistualVM
  * Click on File -> Add JMX Connection... 
  * Enter connection: service:jmx:rmi://localhost:8084/jndi/rmi://localhost:8083/jmxrmi
  * Check [x] Use security credentials
  * Enter username and password
  * Check [x] Do not require SSL connection
  * Click OK button