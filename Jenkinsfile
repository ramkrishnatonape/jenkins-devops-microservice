//Declarative
pipeline {	
	//agent any
	agent { docker { image 'maven:3.6.3' } }
	stages {
		stage('Build') {
			steps {
				sh 'mvn --version'
				echo "Build"
			}
		}

		stage('Test') {
			steps {
				echo "Test"
			}
		}

		stage('Integration Test') {
			steps {
				echo "Integration Test"
			}
		}
	}	
	post {
			always {
				echo 'I always runs'
			}
			success {
				echo 'I run when your successful'
			}
			failure {
				echo 'I run when you failed'
			}
	}		
}
