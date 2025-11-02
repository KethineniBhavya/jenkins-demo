 pipeline {
   agent any
   tools {
     jdk 'jdk-11'
     maven 'Maven-3.8.6'
   }
   stages {
     stage('Checkout Code') {
        steps {
            checkout scm
        }
     }
     stage('Build') {
       steps {
         sh 'mvn -B -DskipTests clean package'
       }
     }
     stage('Test') {
       steps {
           sh 'mvn test'
       }
       post {
         always {
           junit 'target/surefire-reports/**/*.xml'
         }
       }
     }
  }
  post {
    always {
      cleanWs()
    }
 }
}
