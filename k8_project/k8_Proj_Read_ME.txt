Java and Jenkins Installation:

1) Update all software packages on Ubuntu server.
sudo apt-get update
sudo apt-get upgrade

2) Install Java on Ubuntu server.
sudo apt-get install default-jdk
java -version

3) Install Jenkins on Ubuntu server.
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ > \
    /etc/apt/sources.list.d/jenkins.list'
sudo apt-get update
sudo apt-get install jenkins


4) Verify:-
(i) ps -ef | grep jenkins
(ii) Jenkins will be launched as a daemon up on start - Check under /etc/init.d/jenkins
(iii) /etc/default/jenkins will capture configuration parameters for the launch like e.g JENKINS_HOME.

5) launch the Jenkins URLS in the browser:-
<ubuntu_ip_address>:8080

6) Get the Password from the path : /var/lib/jenkins/secrets/initialAdminPassword

---------------------------------------------------------------------------------
/etc/default# cat /var/lib/jenkins/secrets/initialAdminPassword
6aba06880c534f85afba6be0085d2fd9
root@ip-172-31-28-251:/etc/default#
---------------------------------------------------------------------------------

8) Click "Install Suggested Plugins" - Then the installation gets started.

9) Create a new user of your own by giving Name, Email-id, username, password.

10) Then Login into the console and explore Jenkins.

1. Open up the script 
vim /etc/default/jenkins
2. Find this $JENKINS_USER and change to “root”:
$JENKINS_USER="root"
3. Then change the ownership of Jenkins home, webroot and logs:
chown -R root:root /var/lib/jenkins
chown -R root:root /var/cache/jenkins
chown -R root:root /var/log/jenkins
4) Restart Jenkins and check the user has been changed:
service jenkins restart

=================================================================================

Docker Installation:

1) sudo apt install docker.io

2) docker login

=================================================================================

Git Installation:

1) sudo apt install git

=================================================================================

AWS Access Keys