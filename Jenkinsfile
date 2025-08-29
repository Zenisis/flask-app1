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
        stage('build'){
            steps {
                sh '''
                docker build -t ${docker_username}/flask-app:git-${GIT_COMMIT} .
                echo "Docker Image built successfully"

                '''
            }
        }
        stage('tag & push'){
            steps {
                sh '''
                docker tag ${docker_username}/flask-app:git-${GIT_COMMIT} ${docker_username}/flask-app:git-${GIT_COMMIT}
                docker push ${docker_username}/flask-app:git-${GIT_COMMIT}
                echo "Docker Image tagged successfully"
                echo "Docker Image pushed successfully"
                echo "integrated webhook "
                '''
            }
        }

    }
}
