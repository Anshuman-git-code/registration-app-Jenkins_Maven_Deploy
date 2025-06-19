
🚀 CI/CD Pipeline with Jenkins and Docker

This project demonstrates how to set up a complete CI/CD pipeline using Jenkins to build a Java web application with Maven, then deploy it to a Dockerized Tomcat server hosted on a separate Docker-Host EC2 instance.

🔧 Project Overview

✅ What was done:
	1.	Launched Jenkins EC2 Instance (Amazon Linux 2)
	2.	Installed Jenkins and started it as a service
	3.	Installed and configured Maven
	•	Added Maven to the system environment so it’s accessible globally
	4.	Configured Jenkins to use Maven
	•	Installed the Maven Integration plugin
	•	Defined Maven tool under Global Tool Configuration
	5.	Launched Docker-Host EC2 Instance
	•	Enabled password login for SSH access
	6.	Integrated Docker-Host with Jenkins
	•	Used SSH plugin to transfer artifacts and execute remote commands
	7.	Created Jenkins Job
	•	Used Maven to build the Java web application
	•	Copied the .war file to the Docker host
	8.	Wrote a Dockerfile on the Docker-Host to deploy .war to Tomcat
	9.	Automated the build and deployment
	•	Jenkins builds the project and deploys it to a running Tomcat container inside Docker

⸻

📸 Project Screenshots

✅ Jenkins Job - Build and Deploy to Docker Host
<img width="1440" alt="Jenkin-Job-To-Build-And-Copy-Artifact-To-Docker-Server" src="https://github.com/user-attachments/assets/737e8585-de9d-48ad-8f02-90dceca42512" />


⸻

✅ Maven Build Success
<img width="1440" alt="Test-Maven-Build" src="https://github.com/user-attachments/assets/402b66a8-a0fc-4354-893f-4d82fd36f2bb" />


⸻

✅ Dockerfile Created on Docker Host
<img width="1440" alt="Created-dockerfile-at-" src="https://github.com/user-attachments/assets/c27a1b7d-3eb9-418a-81c9-44aff1a54fe3" />


⸻

✅ Automated Build and Deployment
<img width="1440" alt="Automated-build-and-deployment-on-docker-container" src="https://github.com/user-attachments/assets/b31b874c-aefc-421b-a30e-dddec1208ff8" />


⸻

✅ Successful Build on Jenkins
<img width="1440" alt="Build-Success-Automated-build-and-deployment-on-docker-container" src="https://github.com/user-attachments/assets/fcc3e573-fd02-4957-8677-d1cdf5e4dbdf" />


⸻

📁 Jenkins Job Configuration Highlights
	•	Source Code Management: Git repository - https://github.com/Ashfaque-9x/registration-app.git
	•	Build Step: Maven goal clean package
	•	Post-Build Actions:
	•	Transfer .war file to Docker-Host
	•	SSH command to:

docker build -t webapp:v1 .
docker stop registerapp
docker rm registerapp
docker run -d --name registerapp -p 8086:8080 webapp:v1



⸻

🌐 Deployment Output
	•	The application is deployed and served by Tomcat on the Docker host.
	•	You can access it at:
http://<your-ec2-public-ip>:8086/<app-name>

⸻

📚 Skills Demonstrated
	•	Jenkins setup and configuration
	•	Maven build integration
	•	CI/CD pipeline automation
	•	Docker image building and container orchestration
	•	Artifact deployment via SSH
	•	Managing multiple EC2 instances with defined roles

⸻

📌 Prerequisites to Recreate
	•	AWS EC2 Instances (for Jenkins and Docker host)
	•	Java, Maven, Git installed on Jenkins server
	•	Docker and Tomcat setup on Docker host
	•	Inbound rules for port 8086 open on Docker-Host
	•	Jenkins plugins:
	•	Maven Integration
	•	SSH
	•	Git

