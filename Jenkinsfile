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
		script {
			sh 'mvn clean package sonar:sonar'
			}
        }
        
    }
}	
  }  
}