pipeline {
    agent {
        docker {
            image 'node:18'  // Utilisation de l'image officielle Node.js 18
        }
    }

    stages {
        stage('Vérification de Node.js') {
            steps {
                sh 'node -v'  // Vérifie si Node.js est bien installé
                sh 'npm -v'   // Vérifie si npm est bien installé
            }
        }

        stage('Cloner le code') {
            steps {
                git branch: 'master', url: 'https://github.com/19adel/gestion-etablissement.git'
            }
        }

        stage('Installation des dépendances') {
            steps {
                sh 'npm install'  // Installe les dépendances du projet
            }
        }
    }

    post {
        success {
            echo '🎉 Pipeline terminé avec succès !'
        }
        failure {
            echo '⚠️ Une erreur est survenue, vérifiez les logs.'
        }
    }
}
