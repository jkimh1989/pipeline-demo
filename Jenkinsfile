pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      agent any
      steps {
        sh './jenkins/build.sh'
      }
    }

    stage('Buzz Test') {
      agent any
      steps {
        sh './jenkins/test-all.sh'
      }
    }

  }
}