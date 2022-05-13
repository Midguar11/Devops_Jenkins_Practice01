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
- comint and push
- cheking site " http://54.90.114.227:8090/webapp/ "

# Phase 1 Completed

# Phase 2

- Setup Ansible server and add hosts file Tomcat server ip
- setup Ansbile controller acces to Jenkins and Tomcat
- writ new playbok Ansible control /opt/playbook/copyfile.yml
- Dashboard / ManageJenkins / configuration / SSH
- Safe method to ADD beacause dierctli add ssh key not safty
- Setup Name (only reference)
- Setup hostname or ip, username and password ( Ansible server)
- click to test fonfugration, if message from Jenkins " Succes ". Setup is done.
-  Save
- Back Jenkins select the jobs "Hello-world"
- configuaration
- Remove Post-build Actions
- Post Steps select " Send files or execute command over SSH "
- Source files: " webapp/target/*.war "
- Remote directory " //opt//playbooks "
- Ann new task Send files or execute command over SSH
- Exec Command " ansible-playbook /opt/playbooks/copyfile.yml "
ddd


