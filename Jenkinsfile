pipeline { 
    agent any

    environment {
        GIT_REPO = 'https://github.com/19adel/gestion-etablissement.git'
        GIT_BRANCH = 'master' // Remplace par la branche que tu veux cloner
    }

    stages {
        stage('Nettoyage') {
            steps {
                cleanWs()
            }
        }

        stage('Cloner le code') {
            steps {
                script {
                    try {
                        git branch: GIT_BRANCH, url: GIT_REPO
                        echo '✅ Clonage réussi !'
                    } catch (Exception e) {
                        error '❌ Erreur lors du clonage, vérifiez les logs.'
                    }
                }
            }
        }

        stage('Installation des dépendances') {
            steps {
                script {
                    // Change cette ligne selon ta technologie
                    sh 'npm install'  // 🔹 Node.js
                }
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
