\# Jenkins Setup on Azure



\## Step 1: Create an Azure Virtual Machine

\- Sign in to Azure Portal

\- Create a new Ubuntu 20.04 VM

\- Allow inbound ports 22 (SSH) and 8080 (Jenkins)



\## Step 2: Connect to the VM

\- Use SSH from local machine:

&nbsp; ssh azureuser@<VM\_PUBLIC\_IP>



\## Step 3: Install Java

sudo apt update

sudo apt install -y openjdk-11-jdk



\## Step 4: Install Jenkins

wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -

sudo sh -c 'echo deb http://pkg.jenkins.io/debian binary/ > /etc/apt/sources.list.d/jenkins.list'

sudo apt update

sudo apt install -y jenkins



\## Step 5: Start Jenkins Service

sudo systemctl start jenkins

sudo systemctl enable jenkins



\## Step 6: Access Jenkins

\- Open browser and navigate to:

&nbsp; http://<VM\_PUBLIC\_IP>:8080



\## Step 7: Unlock Jenkins

sudo cat /var/lib/jenkins/secrets/initialAdminPassword



\## Step 8: Create a Jenkins Job

\- Create a Freestyle project

\- Add a build step to execute a shell command

\- Example:

&nbsp; echo "Jenkins is running on Azure"

