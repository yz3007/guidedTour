pipeline{
	agent any
	stages{
		stage('Build'){
			steps{
				echo 'Building'
			}
		}
		stage('Test'){
			steps{
				echo 'Testing'
			}
		}
		stage('Deploy - Staging'){
			steps{
				echo './deploy staging'
				echo './run-smoke-tests'
			}
		}
		stage('Sanity check'){
			steps{
				input "Does the staging env look ok?"
			}
		}
		stage('Deploy - Production'){
			steps{
				echo './deploy production'
			}
		}
	
	}
	
	post{
		always {
			echo 'One way or another, I have failed'
			deleteDir()
		}
		success{
			echo 'I succeeded!'
		}
		unstable{
			echo 'I am unstable :/'
		}
		failure{
			echo 'I failed :('
		}
		changed{
			echo 'THings were different before...'
		}
	}

}
