pipeline{
    agent any
    stages {
        stage('拉取代码') {
            steps {
                echo '正在拉取pull...修改了名称Jenkinsfile'
                sh 'ls -al'
            }
        }
        stage('构建项目') {
            steps {
                echo '正在构建Building...'
                sh 'ls -al'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Add deployment commands here
            }
        }
    }

}