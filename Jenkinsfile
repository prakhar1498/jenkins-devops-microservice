pipeline {
	agent any
	stages {
	stage('Build') {
		steps{
		echo "Build"
		}
	}
	stage('Test') {
		steps{
		echo "Test"
		}
	}
	stage('Integration Test') {
		steps{
		echo "Integration Test"
		}
	}
	} 
	
	post {
		always{
			echo "I'm awesome. I run always."
		}
		success{
			echo "I run only when you are successful"
		}
		failure{
			echo "I run when it fails."
		}

	}
}
