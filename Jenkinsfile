pipeline {
    agent any  // Runs on any available Jenkins agent

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/pranjal-munshi/PES1UG22AM117_Jenkins.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    echo 'Compiling hello.cpp...'
                    sh 'g++ -o hello_exec hello2.cpp'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo 'Running tests...'
                    sh './hello_exec'  // Executes the compiled C++ program
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
