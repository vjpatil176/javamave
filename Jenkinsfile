pipeline {
    agent any
    environment {
        PATH = "/opt/maven3.9.6/bin:$PATH"
    }
    stages {
        stage("Clone Code") {
            steps {
               git branch: "main", url: "https://github.com/nnsnarasimha/maven.git"
            }
        }
        stage("Build Code") {
            steps {
                sh "mvn clean install"
            }
        }
     }
 }
