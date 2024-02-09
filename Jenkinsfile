pipeline {
	agent { docker { image 'maven:3.6.3' }
		services :
			-docker:dind
	}
	
	stages {
		stage('Build') {
			steps {
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
	post{
		always{
			echo 'Iam Awesome. I run always'
		}
		success{
			echo 'I run when you are Successful'
		}
		failure{
			echo 'I run when you fail'
		}
	}
}
