pipeline {
    agent any

    // environment {
    //     DOCKER_IMAGE = 'your-image-name:latest'
    //     DOCKER_REGISTRY = 'your-docker-registry'
    //     DOCKER_CREDENTIALS_ID = 'your-docker-credentials-id'
    // }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        // stage('Docker Login') {
        //     steps {
        //         script {
        //             docker.withRegistry("https://${DOCKER_REGISTRY}", DOCKER_CREDENTIALS_ID) {
        //                 echo 'Logged in to Docker registry'
        //             }
        //         }
        //     }
        // }
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
