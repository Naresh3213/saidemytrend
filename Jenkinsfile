pipeline {
    agent any
    environment {
        PATH = "/opt/maven/bin:$PATH"
    }
    
    stages {
      
      stage("build") {
         steps {
            sh 'mvn clean deploy'
         }
      }
      
      stage('SonarQube analysis') {
         environment {
            scannerHome = tool 'SonarQube Scanner'
         }
         
         steps {
           withSonarQubeEnv('sonar-Qube-server') {
               
               sh "${scannerHome}/bin/sonar-scanner"
       
           }
         }
      }
    }
 }
   






















