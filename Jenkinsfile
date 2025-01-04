// pipeline {
//     agent any 



//     stages {
//         stage('Setup') {
//             steps {
//                 script {
                    
//                     bat 'echo "Téléchargement des fichiers requis..."'
//                     // sh 'ls -al'

//                 }
//             }
//         }

//         stage('Run Collection') {
//             steps {
//                 script {
                    
//                     bat '''
//     newman run reqres.postman_collection.json
// '''

//                 }
//             }
//         }

//         stage('Generate Report') {
//             steps {
//                 script {
//                     echo 'Génération du rapport Newman...'
//                     archiveArtifacts artifacts: 'newman-report.html', allowEmptyArchive: true
//                 }
//             }
//         }
//     }

//     post {
//         always {
//             script {
//                 echo 'Pipeline terminé. Consultez les artefacts pour le rapport.'
//             }
//         }
//     }
// }
pipeline {
    agent any
    stages {
        stage('Check Newman Installation') {
            steps {
                script {
                    // Vérifie si Newman est installé
                    bat 'newman -v'
                }
            }
        }
    }
}

