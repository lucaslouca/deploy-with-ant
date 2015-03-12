# deploy-with-ant
Minimalistic ant script for Tomcat war file deployment. 

This script first does a ``mvn clean`` and ``mvn install`` on the defined maven project. It then connects to the provided server, stops the running Tomcat, uploads the newly created .war file to the Tomcat's webapp directory and starts the Tomcat again. This script can be extended to support backing up any existing .war files, log files etc.


 **How to use**
* Adjust the property values to your needs
* ``cd ant``
* Run ``ant``
