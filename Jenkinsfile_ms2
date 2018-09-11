pipeline{
	agent any
	stages {
		stage('Deploy'){
			steps{
				retry(3){
					//sh "./flakey-deploy.sh"
					echo "hello, world"
				}
				
				timeout(time:3, unit:'MINUTES'){
					sh './health-check.sh'
				}
			}
		}
	}
}
