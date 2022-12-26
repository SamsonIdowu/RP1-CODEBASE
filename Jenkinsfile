pipeline {
  agent any

  stages {
    stage('Build and Install Environment') {
      steps {
        sh 'sudo apt-get update'
        sh 'apt-get install nodejs -y'
        sh 'npm install'
        sh 'sudo apt install docker.io && sudo snap install docker'

    }
    stage('Test') {
      steps {
        sh 'npm test'
      }
    }
    stage('Build Docker Image') {
      steps {
        sh 'docker build -t my-webapp .'
      }
    }
    stage('Run Docker Container') {
      steps {
        sh 'docker run -p 3000:3000 my-webapp'
      }
    }
  }
}