pipeline {
<<<<<<< HEAD
  agent any
  stages {
    stage('Clone repository') {
      steps {
        checkout scm
      }
=======
    agent any

    environment {
        IMAGE_NAME = 'dushantashev/kiii-Jenkins'
>>>>>>> 81fda8c (Tret commit)
    }

    stage('Build image') {
      steps {
        script {
          app = docker.build("${IMAGE_NAME}")
        }

      }
    }

    stage('Push image') {
      steps {
        script {
          docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
            app.push("${env.BRANCH_NAME}-${env.BUILD_NUMBER}")
            app.push("${env.BRANCH_NAME}-latest")
          }
        }

      }
    }

  }
  environment {
    IMAGE_NAME = 'mjovanovik/kiii-jenkins'
  }
}