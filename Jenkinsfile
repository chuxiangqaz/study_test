pipeline {
	agent any
	
	parameters {
		string(name:'Branch', defaultValue:'master', description:'请输入要构建的分支')
		string(name:'GitUrl', defaultValue:'https://github.com/chuxiangqaz/study_test', description:'请输入要构建的分支')
		string(name:'GitCredentialsId', defaultValue:'', description:'请输入要构建的分支')
	}
	
	stages {
		stage('代码拉取') {
			steps {
				echo "工作目录：${WORKSPACE}"
				echo "当前目录："
				sh 'pwd'
				echo "分支是 ${Branch}"
				git branch: "${Branch}", credentialsId: "${GitCredentialsId}", url: "${GitUrl}"
				echo "当前目录文件："
				sh "ls -alh"
			}
		}
    }
}
