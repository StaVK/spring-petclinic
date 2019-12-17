pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        bat(script: 'bat "mvn -Dmaven.test.skip=true clean package"', returnStatus: true)
      }
    }

    stage('Testing') {
      parallel {
        stage('Testing') {
          steps {
            sh 'mvn test'
          }
        }

        stage('SonarQube Test') {
          steps {
            sh 'mvn sonar:sonar'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying....'
      }
    }

  }
}