pipeline {
	agent any
	parameters {
		string(name:'branch', defaultValue:'master', description:'请输入要构建的分支')
		choice(name:'mode', choices:['deploy', 'rollback'], description:'选择方向')
		booleanParam(name:'DEBUG_BUILD', defaultValue:true,description:'')
		text(name:'Deploy_text', defaultValue:'One\nTwo\nThree', description:'')
		password(name:'PASSWORD',defaultValue:'',description:'password')
	}
	stages {
		stage('deploy'){
		    steps{

			    echo "参数 ${params.mode}"
		    } 
		}
    }
}
