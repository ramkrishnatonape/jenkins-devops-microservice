//Declarative
pipeline {	
	agent any
	//agent { docker { image 'maven:3.8.5' } }	
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}

	stages {
		stage('checkout') {
			steps {		
				//sh 'mvn --version'
				//sh 'docker --version'
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
			}
		}
		stage("Compile") {
			steps {
				sh "mvn clean compile"
			}
		}
		stage('Test') {
			steps {
				sh "mvn test"
				echo "Test"
			}
		}

		stage('Integration Test') {
			steps {
				sh "mvn failsafe:integration-test failsafe:verify"
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
