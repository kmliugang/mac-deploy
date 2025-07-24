pipeline{
    agent any
    tools {
        nodejs 'nodejs24' // 这里填写你在 Jenkins 配置的名称
    }
    stages {
        stage('构建项目') {
            steps {
                echo '正在构建Building...'
                sh 'ls -al'
                sh 'npm install'
                sh 'npm run docs:build'
                sh 'ls .vitepress/'
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