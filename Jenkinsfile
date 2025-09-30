pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
//         stage('docker login') {
//             steps {
//                 withCredentials([usernamePassword(credentialsId: 'dockerhub', usernameVariable: 'docker_username', passwordVariable: 'docker_password')]) {
//                     sh 'echo $docker_password | docker login -u $docker_username --password-stdin'
//                 }
//             }
//         }
        stage('Build') {
            steps {
                sh "echo demo "
            }
        }
//         stage ('test'){
//           when{
//             branch 'master'

//          }
//          steps{
//             sh '''
//             docker run -d -p 5000:5000 --name flask-test-container flask-app:git-${GIT_COMMIT}
//             sleep 10
//             curl -f http://localhost:5000 || exit 1
//             sleep 5
//             echo "Tests passed successfully"
//             docker stop flask-test-container
//             docker rm flask-test-container  

//             '''
//            }
//         }    
//         stage('Deploy') {
//             when {
//                 branch 'main'
//             }
//             steps {
//                 sh 'docker run -d -p 5000:5000 flask-app:git-${GIT_COMMIT} '
//             }
//         }
//     }
// }
