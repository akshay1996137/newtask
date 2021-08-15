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
      stage('nexus'){
          steps{
             echo 'mvn nexus'
             sh 'nexusArtifactUploader artifacts: [[artifactId: 'junit', classifier: '', file: 'CI-CD2/target/WebAppCal-1.2.4', type: 'war']], credentialsId: 'a6a4c993-0001-41c3-b87f-d157b70dfc97', groupId: 'com.web.cal', nexusUrl: '52.195.5.101:8081', nexusVersion: 'nexus2', protocol: 'http', repository: 'release', version: '1.2.4''
             }
          }
      }
      


      












 }

