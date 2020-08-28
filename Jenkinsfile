pipeline {
  agent any
  stages{
    stage('Build') {
      steps {
        echo "Build Phase"
      }
	}  
    stage('Test') {
      steps {
        echo "Testing Phase"
      }
    }
  stage('Deploy') {
      steps {
        echo "Test Deploy Phase"
      }	  
    }
  stage('Sonarqube1') {
    environment {
        scannerHome = tool 'SonarPLSQL'
    }
    steps {
        withSonarQubeEnv('Sonarqube1') {
            sh "${scannerHome}/bin/sonar-scanner"
        }
        timeout(time: 10, unit: 'MINUTES') {
            waitForQualityGate abortPipeline: true
        }
    }
}	
  }  
}