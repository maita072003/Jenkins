pipeline {
    agent any

    stages {
        stage('Clonar Repositorio') {
            steps {
                git branch: 'main', url: 'https://github.com/maita072003/Jenkins'
                sh 'cd hola-mundo'
            }
        }

        stage('Ejecutar Pruebas') {
            steps {
                sh 'npm test'
            }
        }

        stage('Construcción') {
            steps {
                echo 'Building...'
                sh 'npm run build'
            }
        }

        stage('Despliegue') {
            steps {
                echo 'Desplegando a producción...'
                sh 'npm init -y'
                sh 'node index.js'
            }
        }
    }

    post {
        always {
            echo 'Pipeline completado.'
        }
        success {
            echo 'Pipeline exitoso.'
        }
        failure {
            echo 'Pipeline fallido.'
        }
    }
}