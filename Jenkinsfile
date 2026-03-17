pipeline {
 agent any

 tools {
   nodejs "node18"
 }

 stages {

  stage('Checkout') {
   steps {
    checkout scm
   }
  }

  stage('Install Dependencies') {
   steps {
    bat 'npm ci'
   }
  }

  stage('Run Tests') {
   steps {
    bat 'npm test -- --watchAll=false'
   }
  }

  stage('Build') {
   steps {
    bat 'npm run build'
   }
  }

 }

 post {
  success {
   echo "Build Successful"
  }

  failure {
   echo "Build Failed"
  }
 }
}