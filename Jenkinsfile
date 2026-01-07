pipeline {
  agent any
  stages {
    stage('Check Out') {
      steps {
        git(url: 'https://github.com/srinugalla/moodle-docker.git', branch: 'main')
      }
    }

    stage('list of files') {
      steps {
        sh 'ls -la'
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -f moodle-multistage/Dockerfile .'
      }
    }

    stage('Docker login') {
      environment {
        DOCKERHUB_USER = 'srinugalla'
        DOCKERHUB_PASSWORD = 'Vennela@124'
      }
      steps {
        sh '''echo "$DOCKERHUB_PASSWORD" | docker login -u "$DOCKERHUB_USER" --password-stdin
'''
      }
    }

    stage('Push') {
      steps {
        sh 'docker push srinugalla/moodle-multistage:latest'
      }
    }

  }
}