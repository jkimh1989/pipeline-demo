pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      agent any
      steps {
        sh '''echo "I am a ${BUZZ_NAME}"
./jenkins/build.sh'''
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
  environment {
    BUZZ_NAME = 'Worker Bee'
  }
}