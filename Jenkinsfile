pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building...'
                script {
                    try {
                        docker.withServer('your-docker-server') {
                            docker.image('your-docker-image').pull()
                            docker.image('your-docker-image').run('--rm -v $PWD:/app -w /app your-build-command')
                        }
                    } catch (Exception e) {
                        currentBuild.result = 'FAILURE'
                        error "Failed to build: ${e.message}"
                    }
                }
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                script {
                    try {
                        sh 'your-test-command'
                    } catch (Exception e) {
                        currentBuild.result = 'FAILURE'
                        error "Tests failed: ${e.message}"
                    }
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded! Send notifications, generate reports, etc.'
        }
        failure {
            echo 'Pipeline failed! Send notifications, generate reports, etc.'
        }
    }
}
