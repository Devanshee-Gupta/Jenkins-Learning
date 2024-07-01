# Jenkins-Learning

## Installation on EC2 Instance

- Go to AWS Console
- Go to EC2 Instances
- Launch instance
  
  NOTE : add inbound rule in security group to allow http traffic from port 8080 for Jenkins

## Pre-Requisites for Jenkins :
 - Java (JDK)

### Run the below commands to install Java and Jenkins

Install Java

```
sudo apt update
sudo apt install -y openjdk-11-jre
```

Verify Java is Installed

```
java -version
```

Now, Installing Jenkins

```
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install -y jenkins

```

You can enable the Jenkins service to start at boot with the command:

```
sudo systemctl enable jenkins
```

You can check the status of the Jenkins service using the command:

```
sudo systemctl status jenkins
```

You can start the Jenkins service with the command:

```
sudo systemctl start jenkins
```

### Login to Jenkins using the below URL:

```
http://<ec2-instance-public-ip-address>:8080
```
[You can get the ec2-instance-public-ip-address from your AWS EC2 console page]


After you get access to Jenkins Page it will ask administrator password, for that

      - Run the command to copy the Jenkins Admin Password - 
        sudo cat /var/lib/jenkins/secrets/initialAdminPassword
      - Enter the Administrator password

### Click on Install suggested plugins
Wait for the Jenkins to Install suggested plugins

Create First Admin User or Skip the step [If you want to use this Jenkins instance for future use-cases as well, better to create admin user]

## Jenkins Installation is Successful. You can now start using the Jenkins 


To restart Jenkins, 

from url - 
```
http://<ec2-instance-public-ip>:8080/restart
```
or

from ec2 instance - 
```
sudo systemctl restart jenkins
```


