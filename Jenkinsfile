pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out staging branch'
                git branch: 'staging',
                    url: 'https://github.com/Niranjangowdasd/devops-practicing.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building application'
                sh 'echo "Build successful"'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests'
                sh 'test -f index.html'
                echo 'Test passed'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application'
                sh 'mkdir -p /tmp/devops-app'
                sh 'cp index.html /tmp/devops-app/'
                echo 'Deployment successful'
            }
        }
    }

    post {
        success {
            echo 'CI/CD Pipeline completed successfully!'
        }

        failure {
            echo 'CI/CD Pipeline failed!'
        }
    }
}
