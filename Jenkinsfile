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
                    docker.withRegistry("https://${dockerhub}", docker_username) {
                        echo 'Logged in to Docker registry'
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
