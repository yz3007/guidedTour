pipeline{
	agent any
	stages{
		stage('No-op'){
			steps{
				sh 'ls;exit 1'
			}
		}
	}
	
	post{
		always{
			echo 'One way or another, I have finished'
			deleteDir()/* clean up our workspace */
		}
        success {
            echo 'I succeeeded!'
        }
        unstable {
            echo 'I am unstable :/'
        }
        failure {
            echo 'I failed :('
	    mail to: 'yufei.zhao@wxciv.com',
		 subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
		 body: "SOmething is wrong with ${env.BUILD_URL}"
        }
        changed {
            echo 'Things were different before...'
        }
		
	}
	
}
