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
    sh 'npm ci'
   }
  }

  stage('Run Tests') {
   steps {
    sh 'npm test -- --watchAll=false'
   }
  }

  stage('Build') {
   steps {
    sh 'npm run build'
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