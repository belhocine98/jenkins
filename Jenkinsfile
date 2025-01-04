// pipeline {
//     agent {
//         docker {
//             image 'postman/newman:alpine'
//         }
//     }



//     stages {
//         stage('Setup') {
//             steps {
//                 script {
                    
//                     sh 'echo "Téléchargement des fichiers requis..."'
//                     // sh 'ls -al'

//                 }
//             }
//         }

//         stage('Run Collection') {
//             steps {
//                 script {
                    
//                     sh '''
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
    agent {
        docker {
            image 'postman/newman:alpine'
            args "-v C:/ProgramData/Jenkins/.jenkins/workspace:/workspace"
            label 'docker'
        }
    }
    stages {
        stage('Run') {
            steps {
                script {
                    sh 'docker run -d -t -w /workspace postman/newman:alpine'
                }
            }
        }
    }
}

