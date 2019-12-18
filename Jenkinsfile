pipeline {
    agent any
    environment {
        git_url     = "git@192.168.3.65:jenkins-learn/hello-world.git"
        remote_ip   = "192.168.3.66"
        remote_dir  = "/opt/hello"
    }
    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
        disableConcurrentBuilds()
        timeout(time: 10, unit: 'MINUTES')
        timestamps()
    }
    stages {
        stage('rsync') {
            steps {
                echo 'rsync'
                sh '''
                    rsync -avz --progress -e 'ssh -p 22' --exclude='Jenkinsfile' --exclude='.git' --delete ${WORKSPACE}/  root@$remote_ip:$remote_dir
                '''
            }
        }
        stage('delete') {
            steps {
                echo '清理工作目录'
                cleanWs()
            }
        }
    }
    post {
        success {
            sh "echo 成功了"
        }
        failure {
            sh "echo 失败了"
        }
    }
}
