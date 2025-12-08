pipeline {
    agent any

    tools {
        // "Maven3" y "jdk17" son nombres que configuraremos en Jenkins más adelante
        maven 'Maven3'
        jdk 'jdk17'
    }

    stages {
        stage('Build') {
            steps {
                echo '--- Compilando ---'
                sh 'mvn clean package -DskipTests'
            }
        }

        stage('Test') {
            steps {
                echo '--- Testeando ---'
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo '--- Simulando Despliegue Docker ---'
                // Para evitar errores de permisos en esta prueba inicial, solo haremos un echo
                sh 'echo "Construyendo imagen Docker: docker build -t mi-app:latest ."'
            }
        }
    }
}