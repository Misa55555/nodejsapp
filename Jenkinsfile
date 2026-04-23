pipeline {
    // Acá ocurre la magia: Jenkins levanta un contenedor de Node exclusivo para este Job
    agent {
        docker { 
            image 'node:20-alpine' 
        }
    }
    
    stages {
        stage('Preparación') {
            steps {
                echo '✅ Contenedor Node.js listo. Verificando versión...'
                sh 'node -v'
                sh 'npm -v'
            }
        }
        stage('Instalar Dependencias') {
            steps {
                echo '📦 Instalando librerías del package.json...'
                sh 'npm install'
            }
        }
        stage('Verificación') {
            steps {
                echo '🔍 Verificando que la carpeta node_modules se haya creado correctamente:'
                sh 'ls -la'
            }
        }
    }
}