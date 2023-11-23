# Steps To Create Jenkins Job with Git Repo + Maven + Tomcat Server

## Go to Tomcat server folder and configure below users in "tomcat-users.xml" file (it will be available in tomcat-server conf folder)
<role rolename="manager-gui" />
<role rolename="manager-script" />
<role rolename="admin-gui" />

<user username="tomcat" password="tomact" roles="manager-gui" />
<user username="admin" password="admin" roles="manager-gui,manager-script,admin-gui"/>

## Go to Jenkins Dashboard -> Manage Jenkins --> Manage Plugins -> Goto Available -> Search For "Deploy Container" Plugin -> Install it.

## Create Jenkins Job 
### -> New Item
### -> Enter Item Name (Job Name)
### -> Select Free Style Project & Click OK
### -> Enter some description
### -> Go to "Source Code Management" Tab and Select "Git"
### -> Enter Project "Git Repo URL"
### -> Add Your Github account credentials
### -> Go to "Build tab"

### -> Click on Add Build Step and Select 'Inovke Top Level Maven Targets'

### -> Select Maven and enter goals 'clean package'

### -> Click on 'Post Build Action' and Select 'Deploy war/ear to container' option

### -> Give path of war file (You can give like this also : **/*.war )

### -> Enter Context Path (give project name)

### -> Click on 'Add Container' and select Tomcat version 9.x

### -> Add Tomcat server credentials (give the username & pwd which is having manager-script role)

### -> Enter Tomact Server URL (http://ec2-vm-ip:tomcat-server-port)

### -> Click on Apply and Save





## Run the job now using 'Build Now' option and see see 'Console Output' of job

## Once Job Executed successfully, go to tomcat server dashboard and see application should be displayed.

## Click on the applicaton name (it should display our application)

