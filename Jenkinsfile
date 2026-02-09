pipeline {
    agent any

    stages {
        stage('Build & Run') {
            steps {
                // מביא את הקוד מה-repo
                checkout scm

                // בונה ומריץ את Compose
                sh 'docker-compose up --build --abort-on-container-exit'
            }
        }

        stage('Cleanup') {
            steps {
                // סוגר ומנקה קונטיינרים ורשתות
                sh 'docker-compose down'
            }
        }
    }
}
