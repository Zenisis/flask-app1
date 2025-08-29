pipeline {
    agent any

    

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Docker Login') {
            steps {
                script {
                    withCredentials([usernamePassword(credentialsId: 'dockerhub', usernameVariable: 'docker_username', passwordVariable: 'docker_password')]) {
                        sh 'echo $docker_password | docker login -u $docker_username --password-stdin'
                    }
                }
            }
        }
        // stage('Docker Build & Tag') {
        //     steps {
        //         script {
        //             docker.build(DOCKER_IMAGE)
        //             echo "Docker image built and tagged as ${DOCKER_IMAGE}"
        //         }
        //     }
        // }
    }
}
