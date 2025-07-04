pipeline {
    agent any

    // 1. 添加参数化构建
    // 在这里定义可以在构建时传入的参数
    parameters {
        string(name: 'GREETING_NAME', defaultValue: 'World', description: '要问候的人的名字')
    }

    stages {
        // 我们可以在步骤中使用 params.参数名 来获取参数值
        stage('Personalized Hello') {
            steps {
                echo "你好, ${params.GREETING_NAME}!"
            }
        }
        stage('Checkout Code') {
            steps {
                // 这是标准的从 Git 仓库拉取代码的步骤
                checkout scm
                echo '代码已从 GitHub 检出完毕!'
            }
        }
        stage('Build') {
            steps {
                echo '正在构建...'
                sh 'sleep 3'
                echo '构建完成!'
            }
        }
        stage('Test') {
            steps {
                echo '正在测试...'
                sh 'ls -l' // 打印出当前目录的文件列表
                echo '测试完成!'
            }
        }
    }

    // 2. 添加构建后操作
    // post 块定义了流水线完成后执行的操作
    post {
        // b. 仅在成功时执行
        success {
            echo '太棒了! 本次构建成功!'
        }
        // c. 仅在失败时执行
        failure {
            echo '糟糕! 本次构建失败了!'
            // 你可以在这里添加发送邮件或钉钉通知的步骤
        }
    }
}
