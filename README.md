# Jenkins Practice 01

- setup my home lab
- Jenkins server runing my privat lab ( Dell X720 )
- Setup AWSinstances Tomcat 8.0

# Create Job

- open browser my Jenkins
- create new job
- select maven project and name " hello-world"
- next page select git and add pratice repositor git link
" https://github.com/Midguar11/Devops_Jenkins_Practice01.git "
- Build / Goals and options " clean install package "
- Branch Specifier " change : main "
- Credentials, use Github Credentials

# Deploy The build on AWS Tomcat server

- Create Tomcat Deployer credenitals
- Hello-world configuration
- Select Post-Build Actions /  Deploy war/ear to a container 
- WAR/EAR files " **/*.war "
- Select containersdeploy tpye " Tomcat 8.x remote "
- Credentials " Tomcat Deployer "
- Save
- Build now
- Cheking in browser " http://54.90.114.227:8090/webapp/ " 

# Triggers

- Build Triggers / Poll SCM Chekbox on
- */2 * * * * ( 2 minuts cheking repository)
- Save
- scr\main\webapp| index.jsp changed " Hello, Midguard!  "
