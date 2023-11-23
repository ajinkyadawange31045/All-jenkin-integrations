# Jenkins Pipeline
Sequence of Jobs execution is called as Pipeline
For our application, we will have multiple environments like below
    - DEV
    - SIT
    - UAT
    - PILOT
    - PROD

For every environment, one JENKINS Job will be created
			JENKINS_DEV_JOB -----> DEV Environment (Dev Server)
			JENKINS_SIT_JOB -----> SIT Environment (SIT Server)
			JENKINS_UAT_JOB -----> UAT Environment (UAT Server)
			JENKINS_PILOT_JOB ---> Pilot Environment (Pilot Server)
			JENKINS_PROD_JOB ----> Prod Environment (Prod Server)

If we want to deploy code changes to all environments then it is recommended to create Build Pipeline

By Using Build Pipeline we can execute JENKINS Jobs sequentially.
	
## Requirement
- If code commit happend in git hub then deploy code into DEV Server
- If DEV Server Deployment successful, then deploy code into SIT environment
- If SIT Server deployment successful, then deploy code into UAT environment.

## Steps To Create Jenkins Pipeline
### (1) Create EC2 VM and install Tomcat Server (Dev Server VM)

### (2) Create EC2 VM and install Tomcat Server (SIT Server VM)

### (3) Create EC2 VM and install Tomcat Server (UAT Server VM)

### (4) Create EC2 VM and install Jenkins (Jenkins Server VM)

### (5) Install JDK, Maven, Git, Deploy To Cotainer in Jenkins Server VM

### (6) Create Jobs in Jenkins Server

		  DEV-Job ---> Dev Server
		
		  SIT-Job ---> SIT Server  (SIT Job should execute if DEV-JOB is stable)

		  UAT-Job ---> UAT-Server (UAT job should execute if SIT-JOB is stable)

### (7) Create Jenkins Build Pipeline to execute Jobs in sequence

--------------------------------------------------------------------------------------------------------

**** If we forgot Jenkins Password, then how to recover it ? *****

## Go to /var/lib/jenkins/

	Open  : config.xml file

## Set Value for useSecurity as false

	ex: <useSecurity>false</useSecurity>

## Re-start jenkins and try to access


******* How to change Jenkins Port Number ***********

## Go to root directory

## Go to /etc/sysconfig 

## Open jenkins file and change Jenkins port number

## Restart Jenkins server
