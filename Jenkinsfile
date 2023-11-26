pipeline {
    agent any
    
    stages {
        stage('Declarative: Checkout SCM') {
            steps {
                checkout scm
            }
        }

        stage('Instalacao npm') {
            steps {
                echo 'Instalando...'
                sh 'rm -rf node_modules || true'  
                sh 'npm install'
            }
        }
    }
}
