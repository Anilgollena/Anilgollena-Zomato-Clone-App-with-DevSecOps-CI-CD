# Zomato-Clone-App-with-DevSecOps-CI-CD

![image](https://github.com/user-attachments/assets/66265c3a-0d36-44d5-a031-af650ab31620)

# Steps:-

Step 1 — Launch an Ubuntu(22.04) T2 Large Instance
![Screenshot (1124)](https://github.com/user-attachments/assets/dfa2dd67-c376-4cb6-be92-20e62aebc17b)


Step 2 — Install Jenkins, Docker and Trivy. Create a Sonarqube Container using Docker.

Step 3 — Install Plugins like JDK, Sonarqube Scanner, Nodejs, and OWASP Dependency Check.

Step 4 — Create a Pipeline Project in Jenkins using a Declarative Pipeline

Step 5 — Install OWASP Dependency Check Plugins

Step 6 — Docker Image Build and Push

Step 7 — Deploy the image using Docker

Step 8 — Terminate the AWS EC2 Instances.

# Install Jenkins, Docker and Trivy
#!/bin/bash
sudo apt update -y
#sudo apt upgrade -y
wget -O - https://packages.adoptium.net/artifactory/api/gpg/key/public | tee /etc/apt/keyrings/adoptium.asc
echo "deb [signed-by=/etc/apt/keyrings/adoptium.asc] https://packages.adoptium.net/artifactory/deb $(awk -F= '/^VERSION_CODENAME/{print$2}' /etc/os-release) main" | tee /etc/apt/sources.list.d/adoptium.list
sudo apt update -y
sudo apt install temurin-17-jdk -y
/usr/bin/java --version
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
                  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
                  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
                              /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update -y
sudo apt-get install jenkins -y
sudo systemctl start jenkins
sudo systemctl status jenkins

# Install Docker

sudo apt-get update
sudo apt-get install docker.io -y
sudo usermod -aG docker $USER
newgrp docker
sudo chmod 777 /var/run/docker.sock

# access the sonarqube
docker run -d --name sonar -p 9000:9000 sonarqube:lts-community
![Screenshot (1128)](https://github.com/user-attachments/assets/40952689-cfa3-4b30-8bf7-87c053ca5d42)


# Install Trivy

sudo apt-get install wget apt-transport-https gnupg lsb-release -y
wget -qO - https://aquasecurity.github.io/trivy-repo/deb/public.key | gpg --dearmor | sudo tee /usr/share/keyrings/trivy.gpg > /dev/null
echo "deb [signed-by=/usr/share/keyrings/trivy.gpg] https://aquasecurity.github.io/trivy-repo/deb $(lsb_release -sc) main" | sudo tee -a /etc/apt/sources.list.d/trivy.list
sudo apt-get update
sudo apt-get install trivy -y

#  Install Plugins like JDK, Sonarqube Scanner, NodeJs, OWASP Dependency Check

1 → Eclipse Temurin Installer (Install without restart)

2 → SonarQube Scanner (Install without restart)

3 → NodeJs Plugin (Install Without restart)

4 Docker

5 Docker Commons

6 Docker Pipeline

7 Docker API

8 docker-build-step

# final outputs 
![Screenshot (1130)](https://github.com/user-attachments/assets/7574b547-b4d9-48d4-85af-665d58c96969)

![Screenshot (1126)](https://github.com/user-attachments/assets/c6df8c61-3952-4010-b6e2-d7a18b9743f0)

![Screenshot (1131)](https://github.com/user-attachments/assets/e0e8f25c-266e-491f-965e-4a1d40aab6a5)

![Screenshot (1132)](https://github.com/user-attachments/assets/d6b569f3-c984-4281-847a-043d630f9de5)

image uploaded into the dockerhub

![image](https://github.com/user-attachments/assets/d8e3e293-1291-4c51-b2d7-9e45bc2b523d)





