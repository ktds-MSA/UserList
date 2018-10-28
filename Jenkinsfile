pipeline {
	agent any

	stages {
		stage ('Compile Stage') {
			steps {
				withMaven(maven : 'maven_3_5_4') {
				    sh 'mvn clean compile'
				}
			}
		}
		stage ('Testing Stage') {
			steps {
				withMaven(maven : 'maven_3_5_4') {
				    sh 'mvn surefire-report:report-only'
				}
			}
		}
		stage('Docker Push'){
			steps {
				sh "${JENKINS_HOME}/script/pushbyhost.sh"
			}
		}
		stage('Deploy'){
			steps {
				sh "${JENKINS_HOME}/script/deploybyhost.sh"
			}
		}
	}
}