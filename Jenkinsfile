pipeline {
    agent any

    tools {
        maven 'Maven 3.9.2'
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Hydhar/jenkinsCICDjava.git'
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

        stage('Report') {
            steps {
                junit '**/target/surefire-reports/*.xml'
            }
        }
    }

    post {
        success {
            echo 'Build and tests completed successfully!'
        }
        failure {
            echo 'Build or tests failed.'
        }
    }
}
