pipeline {
    agent any
    stages {
        stage("Code") {
            steps {
                echo "Cloning the code"
                git url: "https://github.com/iamakash-cyber/django-notes-app.git", branch: "main"
            }
        }
        stage("Build") {
            steps {
                echo "Building the Docker image"
                sh "docker build -t my-note-app ."
            }
        }
        stage("Deploy") {
            steps {
                echo "Deploying the Docker container"
                sh "docker-compose down && docker-compose up -d"
            }
        }
    }
}
