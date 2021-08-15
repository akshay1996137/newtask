pipeline {
    agent any
   
    stages {

       stage('mvn compile'){
          steps {
             echo 'mvn compile'
             sh 'mvn compile'
          }
       }  

       
       stage('mvn test'){
          steps {
             echo 'mvn test'
             sh 'mvn test'
          }
       }


      stage('sonar test'){
          steps {
             withSonarQubeEnv('SonarQube') {
             echo 'sonar test'
             sh 'mvn sonar:sonar'
             } 
          }
      } 
      
      stage('mvn package'){
          steps{ 
             echo 'mvn package'
             sh 'mvn package'
             }
          }
      } 
      












 }

