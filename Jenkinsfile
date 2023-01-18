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
    stage('deploy') {
           steps {
               sshagent(['deploy-user']) {
    sh "scp -o StrictHostKeyChecking=no target/hello-world-maven.war ec2-user@3.109.122.94:/opt/tomcat/webapps"
}
   } 
 }
  }
}
