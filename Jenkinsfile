pipeline {
	agent any
	stages {
		stage('deploy to test'){
			steps{
				echo '输出变量 ${env.GIT_BRANCH}'

				script{
					if (env.GIT_BRANCH == 'test'){
						echo "deploy to test env"
					}
				}
			}
		}
		
		stage('deploy to prod'){
			steps{
				script{
					if (env.GIT_BRANCH == 'master'){
						echo "deploy to prod env"
					}
				}
			}
		}
	}
}
