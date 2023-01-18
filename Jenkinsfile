pipeline {
    agent any
    tools { 
        maven 'maven_home' 
        
           }
stages {
      stage('GIT checkout') {
           steps {
                git branch: 'main', url: 'https://github.com/akshugithub/CI-CD-Pipeline-with-Jenkins-deploy-tomcat.git'
               
               }
      }
               
       stage('Compile') {
           steps {
               sh 'mvn clean test package'
            }
        }
        
stage('Build') {
           steps {
               sh 'mvn clean install'
           }
}           
  }
}
