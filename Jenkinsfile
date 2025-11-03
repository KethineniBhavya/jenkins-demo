pipeline {
    agent any

    tools {
        maven 'Maven 3.9.11' // Replace with the name of your Maven tool configured in Jenkins
        jdk 'JDK 17'         // Replace with the name of your JDK configured in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'git@github.com:KethineniBhavya/jenkins-demo.git', credentialsId: 'your-ssh-credential-id'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
    }

    post {
        success {
            echo 'Build completed successfully!'
        }
        failure {
            echo 'Build failed.'
        }
    }
}
