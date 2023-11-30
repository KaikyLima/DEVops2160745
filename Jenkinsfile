    agent any

    stages {
        stage('Instalacao npm'){
            steps {
                echo 'Instalando...'
                sh '''
                    
                    npm install
                '''
            }
        }
        stage('Testes do npm'){
            steps {
                echo 'Testando...'
                sh '''
                    
                    npm test
                '''
            }
        }
        stage('Building'){
            steps {
                echo 'Buildando...'
                sh '''
                    
                    docker build
                '''
            }
        }
        stage('Subindo containers'){
            steps{
                echo 'Ativando containers...'
                sh'''
                    docker compose up
                '''
            }
        }
    }