pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Clona el repositorio desde GitHub
                git url: 'https://github.com/ttedann/conexionpipe.git', branch: 'main'
            }
        }
        stage('Build') {
            steps {
                // Ejecuta el comando Maven para compilar el proyecto
                script {
                    def mvnHome = tool name: 'Maven', type: 'hudson.tasks.Maven$MavenInstallation'
                    sh "${mvnHome}/bin/mvn clean install"
                }
            }
        }
        stage('Test') {
            steps {
                // Ejecuta los tests del proyecto usando Maven
                script {
                    def mvnHome = tool name: 'Maven', type: 'hudson.tasks.Maven$MavenInstallation'
                    sh "${mvnHome}/bin/mvn test"
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    echo 'Deploying conexionpipe application...'
                    // Aquí puedes añadir otros pasos de despliegue específicos
                }
            }
        }
    }
}
