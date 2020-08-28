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
  stage('Sonarqube') {
    environment {
        scannerHome = tool 'SonarPLSQL'
    }
    steps {
        withSonarQubeEnv('Sonar_Jenkins') {
            sh "${scannerHome}/bin/sonar-scanner"
        }
        timeout(time: 10, unit: 'MINUTES') {
            waitForQualityGate abortPipeline: true
        }
    }
}	
  }  
}