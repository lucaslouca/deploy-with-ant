# Build with Maven and deploy with Ant
Minimalistic ant script for Tomcat war file deployment. 

This script first does a ``mvn clean`` and ``mvn install`` on the defined maven project. It then connects to the provided server, stops the running Tomcat, uploads the newly created .war file to the Tomcat's webapp directory and starts the Tomcat again.


 **How to use**
 
* Adjust the property values in ``ant/build.xml`` to your needs
* ``cd ant``
* Run ``ant``


This script can be extended to support backing up any existing .war files, log files etc.

###Alternative execution of ``mvn clean install``
```
<target name="maven-clean-install" description="Builds the individual project">
  <exec dir="${maven.project.path}" executable="sh">
    <arg value="-c"/>
    <arg value="mvn"/>
    <arg line="clean install" />
  </exec>
</target>
```
or under Windows
```
<target name="maven-clean-install" description="Builds the individual project">
  <exec dir="${maven.project.path}" executable="cmd">
    <arg value="/c"/>
    <arg value="mvn"/>
    <arg line="clean install" />
  </exec>
</target>
```
