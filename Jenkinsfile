pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'python3 -m venv venv'
                sh '. venv/bin/activate && pip install -r requirements.txt'
            }
        }
        stage('Test') {
            steps {
                sh '. venv/bin/activate && python3 -m pytest test_app.py -v'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo "✅ Despliegue simulado correctamente en $(date)"'
            }
        }
    }
    post {
        success {
            echo '🎉 Pipeline completado con éxito'
        }
        failure {
            echo '❌ Pipeline fallido, revisa los logs'
        }
    }
}
