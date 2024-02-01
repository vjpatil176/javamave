pipeline {
    agent any
    environment {
        PATH = "/opt/maven3.9.6/bin:$PATH"
    }
    stages {
        stage("Git pull") {
            steps {
               git branch: "master", url: "https://github.com/vjpatil176/javamave.git"
            }
        }
        stage("Maven Build") {
            steps {
                sh "mvn clean install"
            }
        }
            stage("DeployStaging") {
            steps {
        sshagent(['deployuser']) {
                sh "scp -oStrictHostKeyChecking=no /var/lib/jenkins/workspace/maven-build-code/webapp/target/webapp.war ec2-user@172.31.71.116:/opt/apache-tomcat-10.1.17/webapps"
                }
            }
         }
     }
  }


