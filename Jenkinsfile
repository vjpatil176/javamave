pipeline {
    agent any
    environment {
        PATH = "/opt/maven3.9.6/bin:$PATH"
    }
    stages {
        stage("Git clone") {
            steps {
               git branch: "main", url: "https://github.com/vjpatil176/javamave.git"
            }
        }
        stage("Maven Build") {
            steps {
                sh "mvn clean install"
            }
        }
     }
 }

