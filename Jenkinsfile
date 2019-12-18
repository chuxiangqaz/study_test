pipeline {
	agent any
	parameters {
		choice(name:'app_env', choices:['dev', 'test', 'prod'], description:'选择方向')
	}

	def user = ''
	def RemoteLogin=
	def RemoteLoginPort = 22
	def RemoteDir = ''
	def GitUrl = 'ssh://git@gitlab-ce.k8s.tools.vchangyi.com:32201/project/shell/audit/php_api.git'
	if (params.app_env == 'dev') {
		RemoteLogin = 'www@42.159.159.9'
		RemoteLoginPort = 22
		RemoteDir = /data/wwwroot/shell-audit.vchangyi.com/api/dev
	}

	if (params.app_env == 'test') {
		RemoteLogin = 'www@42.159.159.9'
		RemoteLoginPort = 22
		RemoteDir = /data/wwwroot/shell-audit.vchangyi.com/api/test
	}

	if (params.app_env == 'prod') {
		RemoteLogin = 'www@42.159.159.9'
		RemoteLoginPort = 22
		RemoteDir = /data/wwwroot/shell-audit.vchangyi.com/api/prod
	}
	
	stages {
	    	// 拉取代码
	        stage('代码拉取') {
	            steps {
	            	echo "工作目录：${RemoteLogin}"
	            	echo "工作目录：${RemoteDir}"
	            }
	        }
	}
}
