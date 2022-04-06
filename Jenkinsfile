//Declarative
pipeline {	
	//agent any
	agent { docker { image 'maven:3.8.5' } }	
	stages {
		stage('Build') {
			steps {				
				echo "Build"
				sh 'maven --version'
				echo "$PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "$env.JOB_NAME"
				echo "$env.BUILD_TAG"
				echo "$env.BUILD_URL"
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
