pipeline {
	agent any

	stages {
		/*stage ('Compile Stage') {
			steps {
				    sh 'mvn clean compile -f pom.xml'
				
			}
		}*/
		stage ('Testing Stage') {
			steps {
				    sh 'mvn surefire-report:report-only -f pom.xml'
			
			}
		}
		
	}
}
