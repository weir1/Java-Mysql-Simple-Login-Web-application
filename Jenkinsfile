pipeline {
  agent {
    node {
      label 'maven_slave'
    }

  }
  stages {
    stage('Deploy') {
      steps {
        retry(count: 3) {
          echo 'hello'
        }

        timeout(time: 3) {
          sleep 5
        }

      }
    }

    stage('test') {
      steps {
        withSonarQubeEnv(installationName: 'sonarqube-8.9.2', credentialsId: 'sonarqube_token')
      }
    }

  }
}