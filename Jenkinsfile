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

    stage('SonarQube analysis') {
//    def scannerHome = tool 'SonarScanner 4.0';
        steps{
        withSonarQubeEnv('sonarqube-8.9.2') { 
        // If you have configured more than one global server connection, you can specify its name
//      sh "${scannerHome}/bin/sonar-scanner"
          
      }
    }

  }
}
