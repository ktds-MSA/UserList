pipeline {
	agent any

	stages {
		stage ('Compile Stage') {
			steps {
				    sh 'mvn clean compile -f spring-boot-demo/pom.xml'
				
			}
		}
		stage ('Testing Stage') {
			steps {
				    sh 'mvn surefire-report:report-only -f spring-boot-demo/pom.xml'
			
			}
		}
		
	}
}
