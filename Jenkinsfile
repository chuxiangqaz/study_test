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
		stage('pre deploy'){
            steps{
                script{
                    approvalMap = input (
                        message: '准备发布到哪个环境？',
                        ok: '确定',
                        parameters:[
                            choice(name: 'ENV',choices: 'test\npre\nprod',description: '发布到什么环境？'),
                            string(name: 'myparam',defaultValue: '',description: '')
                        ],
                        submitter: 'admin',
                        submitterParameter: 'APPROVER'
                    )
                }
            }
        }
        stage('deploy'){
            steps{
                echo "操作者是 ${approvalMap['APPROVER']}"
                echo "发布到什么环境 ${approvalMap['ENV']}"
                echo "自定义参数 ${approvalMap['myparam']}"
            }
        }
    }
}
