pipeline {
 agent any
 
 tools {
 maven 'Maven 3.9.2' // Make sure this matches your Maven installation name in Jenkins
 }
 
 environment {
 GIT_REPO = 'https://github.com/Hydhar/jenkinsCICDjava.git'
 }
 
 stages {
 stage('Checkout') {
 steps {
 echo 'Checking out source code from GitHub...'
 git url: "${env.GIT_REPO}", branch: 'master'
 }
 }
 
 stage('Build') {
 steps {
 echo 'Building the project using Maven...'
 bat 'mvn clean install'
 }
 }
 
 stage('Test') {
 steps {
 echo 'Running unit tests...'
 bat 'mvn test'
 }
 }
 
 stage('Test Report') {
 steps {
 echo 'Publishing JUnit test results...'
 junit '**/target/surefire-reports/*.xml'
 }
 }
 }
 
 post {
 success {
 echo '✅ Build and tests completed successfully!'
 }
 failure {
 echo '❌ Build or tests failed. Check the logs for details.'
 }
 }
} 
