pipeline {
	agent any
	parameters {
		string(name:'branch', defaultValue:'master', description:'请输入要构建的分支')
		choice(name:'mode', choices:['deploy', 'rollback'], description:'选择方向')
	}
	stages {
        stage('test') {
            steps{
				echo '输出变量'
                echo $mode
            }  
        }
    }
}
