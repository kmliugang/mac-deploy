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
        // 打包制品，让jenkins可以找到制品
        stage('打包制品') {
            steps{
                // 切换目录
                dir('.vitepress/dist') {
                    echo '切换到 .vitepress/dist 目录'
                    sh 'ls -al'
                    sh 'tar -zcvf docs.tar.gz *'
                    archiveArtifacts artifacts: 'docs.tar.gz', allowEmptyArchive: true, fingerprint: true,onlyIfSuccessful: true
                    echo '打包完成，制品已归档'

                }
            }
        }
        stage('部署') {
            steps {
                echo 'Deploying...'
                dir('.vitepress/dist') {
                    echo '切换到 .vitepress/dist 目录'
                    sh 'ls -al'
                    // 假设你有一个部署脚本 deploy.sh
                    // sh './deploy.sh'
                    writeFile file: 'Dockerfile', text: '''FROM nginx
                    ADD docs.tar.gz /usr/share/nginx/html'''
                    sh 'cat Dockerfile'
                    sh 'docker build -f Dockerfile -t docs-app:latest .'
                    sh 'docker rm -f app'
                    sh 'docker run -d --name app -p 8080:80 docs-app:latest'
                }
            }
        }
    }

}