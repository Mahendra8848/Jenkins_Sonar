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
    steps {
        
            sonar.host.url="http://localhost:9000"
			sonar.login=admin
			sonar.password=admin

			sonar.projectKey=firstsqlproject
			sonar.projectName="First PLSQL Project"
			sonar.projectVersion="1.0"
			sonar.projectDescription="PL/SQL demo"
			sonar.sources="."
			sonar.sourceEncoding="UTF-8"
			sonar.inclusions="**/*.sql"
        
    }
}	
  }  
}