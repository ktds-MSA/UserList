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
		stage('Docker Push'){
			
				sh "${JENKINS_HOME}/script/pushbyhost.sh"
			
		}
		stage('Deploy'){
				sh "${JENKINS_HOME}/script/deploybyhost.sh"
		}
	}
}
