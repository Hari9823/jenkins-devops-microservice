pipeline {
	agent any 
	environment{
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage('Checkout') {
			steps {
				echo "Build"
				echo "Path - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
			}
		}
		stage('Compile'){
			steps{
				sh "maven clean compile"
			}
		}
		stage('Test') {
			steps {
				sh "maven test"
			}
		}
		stage('Integration Test') {
			steps {
				sh  "maven failsafe:integration-test failsafe:verify"
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
