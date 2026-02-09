pipeline {
    agent any

    stages {
        stage('Build & Run') {
            steps {
                // מביא את הקוד מה-repo
                checkout scm

                bat 'docker compose down --remove-orphans'
                // בונה ומריץ את Compose
                bat 'docker-compose up --build --abort-on-container-exit'
            }
        }

        stage('Cleanup') {
            steps {
                // סוגר ומנקה קונטיינרים ורשתות
                bat 'docker-compose down'
            }
        }
    }
}
