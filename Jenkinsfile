pipeline{
    agent any
    stages {
        stage('构建项目') {
            steps {
                echo '正在构建Building...'
                sh 'ls -al'
                sh 'npm install'
                sh 'npm run docs:build'
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