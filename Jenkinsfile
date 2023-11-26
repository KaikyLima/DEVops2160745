pipeline {
    agent any
    
    options {
        cachesNodeModules()
    }

    stages {
        stage('Declarative: Checkout SCM') {
            steps {
                checkout scm
            }
        }

        stage('Instalacao npm') {
            steps {
                echo 'Instalando...'
                sh 'rm -rf node_modules'
                sh 'npm install'
            }
        }
    }
}
