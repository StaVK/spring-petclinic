pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        bat(script: 'bat "mvn -Dmaven.test.skip=true clean package"', returnStatus: true)
      }
    }

  }
}