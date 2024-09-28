pipeline {
    agent any

    tools {
        nodejs 'NodeJS_Installation_Name' // El nombre que definiste en las herramientas globales de Jenkins
    }

    stages {
        stage('Clonar Repositorio') {
            steps {
                git branch: 'main', url: 'https://github.com/maita072003/Jenkins'
                sh 'cd hola-mundo'
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