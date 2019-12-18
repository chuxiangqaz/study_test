pipeline {
	agent any
	paramesters {
		string(name:'branch', defalutBalue:'master', description:'请输入要构建的分支')
		choice(name:'mode', choices:['deploy', 'rollback'], description:'选择方向')
		
	}
}
