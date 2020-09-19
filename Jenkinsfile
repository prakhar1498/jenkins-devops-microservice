pipeline {
	agent any
	environment
	{
		dockerhome = tool 'myDocker'
		mavenhome = tool 'myMaven'
		PATH = "$dockerhome/bin:$mavenhome/bin:$PATH"
	}
	stages {
	stage('Checkout') {
		steps{
		echo "Build"
		sh 'mvn --version'
		sh 'docker version'	
		echo "$PATH"
		echo "BUILD NUMBER - $env.BUILD_NUMBER"
		echo "BUILD ID - $env.BUILD_ID"
		echo "JOB NAME - $env.JOB_NAME"
		echo "BUILD TAG - $env.BUILD_TAG"
		echo "BUILD URL - $env.BUILD_URL"
		}
	}
	stage('Compile') {
		steps{
		sh "mvn clean compile"
		}
	}	
	stage('Test') {
		steps{
		sh "mvn test"
		}
	}
	stage('Integration Test') {
		steps{
		sh "mvn failsafe:integration-test failsafe:verify"
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
