pipeline {
  agent any
  stages {
    stage('Check Out') {
      steps {
        git(url: 'https://github.com/srinugalla/moodle-docker/tree/main/moodle', branch: 'main')
      }
    }

  }
}