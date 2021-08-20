# How to Manually Install a Jenkins Slave

## Intro
Tools for installing Jenkins Agent as a windows service

## Steps
1. Log into the Jenkins controller and create the new node

2. Log onto the agent. Create a new working directory for the Jenkins . Example: **C:\Apps\Jenkins-Home**

3. Copy the following files to the new folder
    - jenkins-agent.exe
    - jenkins-agent.xml
    - jenkins-agent.exe.config


1. Open a Windows command line as Administrator.

2. Navigate to the directory where the jenkins-slave.exe is installed. Example: 

    `cd C:\Apps\Jenkins-Home`

3. Install the service 

    `jenkins-agent.exe install`

4. After the service has been succesfully installed, a message similar to the following should appear

    `2021-08-22 10:17:30,486 INFO - Installing the service with id 'jenkins-agent'`

5. Right click Windows start button, select Run, then enter "services.msc" to open Windows Service management console.
Scroll down until you find the 'jenkins-agent' Windows service.

6. Update the service to run as a service account. Right click the 'jenkins-agent' service, select properties.  

6. Right click the service and select 'Start' to start the service

## Managing the services
1. To change the service name:

    `$ sc config <service-name> displayname="jenkins-agent-1"`

2. To delete a service:

    `sc delete <service-name>`

## References
https://www.jenkins.io/doc/book/using/using-agents/
https://support.cloudbees.com/hc/en-us/articles/217423827-How-to-Install-Several-Windows-Agents-as-a-Service-?page=76
https://github.com/winsw/winsw/blob/master/doc/installation.md
https://github.com/winsw/winsw/blob/master/doc/xmlConfigFile.md

https://stackoverflow.com/questions/44751960/install-jenkins-slave-as-a-windows-service-in-command-line

In case of PKIX error: 
https://support.cloudbees.com/hc/en-us/articles/217078498-PKIX-path-building-failed-error-message?page=76

Original WinSW
https://repo.jenkins-ci.org/ui/native/releases/com/sun/winsw/winsw/2.9.0

WinSW .xml examples
https://github.com/winsw/winsw/tree/v3/samples

