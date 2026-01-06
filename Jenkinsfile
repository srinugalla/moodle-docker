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

  }
}