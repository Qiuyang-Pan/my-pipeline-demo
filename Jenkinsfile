// 这是一个声明式 Pipeline 的基本结构
pipeline {
    // agent any 表示这个流水线可以在任何可用的 Jenkins agent 上运行
    agent any

    // stages 是所有阶段的容器
    stages {
        // stage 是一个具体的阶段，比如 "构建" 或 "测试"
        stage('Hello') {
            // steps 是一个阶段里具体执行的步骤
            steps {
                echo '你好, Jenkins Pipeline!'
            }
        }
        stage('Build Simulation') {
            steps {
                echo '正在模拟构建过程...'
                // 使用 sh 命令执行 shell 脚本
                sh 'sleep 3' // 模拟耗时操作
                echo '构建完成!'
            }
        }
        stage('Test Simulation') {
            steps {
                echo '正在模拟测试过程...'
                sh 'sleep 2' // 模拟耗时操作
                echo '测试完成!'
            }
        }
    }
}
