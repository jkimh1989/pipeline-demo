pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      agent any
      steps {
        sh './jenkins/build.sh'
        archiveArtifacts(artifacts: 'target/*.jar', fingerprint: true)
      }
    }

    stage('Buzz Test') {
      agent any
      steps {
        sh './jenkins/test-all.sh'
        junit 'target/**/TEST*.xml'
      }
    }

  }
}