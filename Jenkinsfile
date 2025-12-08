//veremos
pipeline {
    agent any
    tools {
        maven 'Maven3'
        jdk 'jdk17'
    }
    stages {
        stage('Build') {
            steps {
                echo '--- Compilando ---'
                bat 'mvn clean package -DskipTests'  // <--- Cambiado a bat
            }
        }
        stage('Test') {
            steps {
                echo '--- Testeando ---'
                bat 'mvn test'                       // <--- Cambiado a bat
            }
        }
        stage('Deploy') {
            steps {
                echo '--- Simulando Despliegue ---'
                bat 'echo "Construyendo imagen..."'  // <--- Cambiado a bat
            }
        }
    }
}