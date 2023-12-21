pipeline {
    agent any
    environment {
        PATH = "/opt/maven3.9.6/bin:$PATH"
    }
    stages {
        stage("Git clone") {
            steps {
               git branch: "master", url: "https://github.com/vjpatil176/javamave.git"
            }
        }
        stage("Maven Build") {
            steps {
                sh "mvn clean install"
            }
        }
	stage('build && SonarQube analysis') {
	    steps{
	        withSonarQubeEnv('sonarqube-10.3') {
		     // optionally use a Maven environment you've configured already
                	sh 'mvn sonar:sonar'
              } 
           }  
        } 
     }
  }

