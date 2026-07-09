pipeline {
    agent any

    stages {
        stage('Cloning repo') {
            steps {
                git 'https://github.com/shashankJ17/static-wed-hosting-via-docker.git'
            }
        }
        stage('Build image via Dockerfile') {
            steps {
                bat 'docker build -t static-img .'
            }
        }
        stage('Creating container via Dockerfile img') {
            steps {
               bat 'docker run -d -p 180:80 --name static-con1 static-img'
            }
        }
        stage('Pushing image to Docker hub') {
            steps {
              bat '''docker login -u shashankj017 -p Shank@4518
                     docker tag static-img shashankj017/static-img:a1
                     docker push  shashankj017/static-img:a1'''
            }
        }
    }
}
