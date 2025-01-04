pipeline {
    agent {
        docker {
            image 'postman/newman:alpine'
        }
    }



    stages {
        stage('Setup') {
            steps {
                script {
                    
                    sh 'echo "Téléchargement des fichiers requis..."'
                    // sh 'ls -al'

                }
            }
        }

        stage('Run Collection') {
            steps {
                script {
                    
                    sh '''
    newman run reqres.postman_collection.json  
'''

                }
            }
        }

        stage('Generate Report') {
            steps {
                script {
                    echo 'Génération du rapport Newman...'
                    archiveArtifacts artifacts: 'newman-report.html', allowEmptyArchive: true
                }
            }
        }
    }

    post {
        always {
            script {
                echo 'Pipeline terminé. Consultez les artefacts pour le rapport.'
            }
        }
    }
}
