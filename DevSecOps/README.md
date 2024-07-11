# End to End DevSecOps Project for DevOps Engineers
# In this project, we will learn about DevOps and DevSecOps tools in one project:
#Tools Covered:
-Linux
-Git and GitHub
-Docker
-Docker-compose
-Jenkins CI/CD
-SonarQube
-OWASP
-Trivy

# Pre-requisites to implement this project:
- AWS EC2 instance (Ubuntu) with instance type t2.large and root volume 29GB.

- Jenkins installed
   - Reference: Jenkins installation
-Docker and docker-compose installled

    - sudo apt-get update
    - sudo apt-get install docker.io -y
    - sudo apt-get install docker-compose -y

-Trivy installed
    - Reference: Trivy Installation
-SonarQube Server installed
    - docker run -itd --name sonarqube-server -p 9000:9000 sonarqube:lts-community

# Steps for Jenkins CI/CD:
1. Access Jenkins UI and setup Jenkins
2. Plugins Installation:
 - Go to Manage Jenkins, click on Plugins and install all the plugins listed below, we will require for other tools integration:
    -SonarQube Scanner (Version2.16.1)
    -Sonar Quality Gates (Version1.3.1)
    -OWASP Dependency-Check (Version5.4.3)
    -Docker (Version1.5)

3. Go to SonarQube Server and create token
  - Click on Administration tab, then Security , then Users and create Token.
  - Create a webhook to notify Jenkins that Quality gates scanning is done. (We will need this step later)
  - Go to SonarQube Server, then Administration , then Configuration and click on Webhook , add webhook in below Format:
http://<jenkins_url>:8080/sonarqube-webhook/
  Example: http://34.207.58.19:8080/sonarqube-webhook/

4. Go to Jenkins UI Manage Jenkins , then Credentials and add SonarQube Credentials.

5. Now, It's time to integrate SonarQube Server with Jenkins, go to Manage Jenkins , then System and look for SonarQube Servers and add SonarQube.

6. Go to Manage Jenkins , then tools , look for SonarQube Scanner installations and add SonarQube Scanner.
    Note: Add name as Sonar

7. Integrate OWASP with Jenkins, go to Manage Jenkins , then tools , look for Dependency-Check installations and add Dependency-Check.
   Note: Add name as dc

8. For trivy, we have already installed it, in pre-reuisites.
   trivy --version

9. Now, It's time to create a CI/CD pipeline in Jenkins:
  - Click on New Item and give it a name and select Pipeline.
  - Select GitHub Project and paste your GitHub repository link.
  - Scroll down and in Pipeline section select Pipeline script from SCM, because our Jenkinsfile is present on GitHub.

10. At last run the pipeline and after sometime your code is deployed using DevSecOps.
11. Congratulations!!! You have done it

If you find any issue during the execution of this project, let me know on LinkedIn

Happy Learning :)





