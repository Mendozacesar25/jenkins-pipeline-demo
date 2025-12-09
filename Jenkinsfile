// prueba funcionamiento

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
                bat 'mvn clean package -DskipTests'
            }
        }

        stage('Test') {
            steps {
                echo '--- Ejecutando Pruebas ---'
                bat 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo '--- Simulando Despliegue ---'
                bat 'echo "Desplegando aplicacion..."'
            }
        }
    }

    // --- NUEVA SECCIÓN DE NOTIFICACIONES ---
    post {
        always {
            // Esto se ejecuta siempre, falle o no
            echo 'El pipeline ha terminado.'
        }
        success {
            echo '✅ ÉXITO: El pipeline pasó correctamente.'
            // Para enviar email real (requiere configuración SMTP en Jenkins):
            // mail to: 'tu-email@ejemplo.com',
            //      subject: "Éxito: Pipeline ${currentBuild.fullDisplayName}",
            //      body: "Todo salió bien. Puedes ver los logs aquí: ${env.BUILD_URL}"
        }
        failure {
            echo '❌ ERROR: El pipeline falló.'
            // mail to: 'tu-email@ejemplo.com',
            //      subject: "Fallo: Pipeline ${currentBuild.fullDisplayName}",
            //      body: "Algo salió mal. Revisa los logs: ${env.BUILD_URL}"
        }
    }
}