pipeline {
    agent any
    tools {
         maven 'maven3'
    }
    stages{
        stage('Build'){
            steps{
                  sh script: 'mvn clean package'
            }
        }
        stage('Upload War To Nexus'){
            steps{
                nexusArtifactUploader artifacts:[
                   [
                        artifactId: 'RegisterPage',
                       classifier: '',
                       file: '/var/lib/jenkins/jobs/myTestpipeline/config.xml',
                      type: 'xml'
                 ]
             ],
                   credentialsId: '623a7bba-d3ad-4186-9ff7-62c633b5722c',
                   groupId: 'org.example',
                   nexusUrl: '18.222.150.10:8081',
                   nexusVersion: 'nexus3',
                   protocol: 'http',
                   repository: 'book-store1',
                   version: '1.0-SNAPSHOT'
  
            }
        }
    }
 }
