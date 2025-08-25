pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage(docker login) {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerhub', usernameVariable: 'docker_username', passwordVariable: 'docker_password')]) {
                    sh 'echo $docker_password | docker login -u $docker_username --password-stdin'
                }
            }
        }
        stage('Build') {
            steps {
                sh "docker build -t flask-app ."
            }
        }
        stage('Test') {
            steps {
                sh 'docker tag flask-app kartik2311/flask-app:git-${GIT_COMMIT}'
                sh 'docker push kartik2311/flask-app:git-${GIT_COMMIT}'
            }
        }
        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
                sh 'docker run -d -p 5000:5000 flask-app:git-${GIT_COMMIT} '
            }
        }
    }
}