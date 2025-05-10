@Library ("shared") _
pipeline {
    agent { label "vinod" }

    stages {
        stage('Code') {
            steps{
                script{
                    clone ("https://github.com/Muhammad-hanzala/django-notes-app.git" , "dev")
                } 
            }
        }

        stage('Build') {
            steps {
                script{
                    docker_build("notes-app","latest","Muhammad-hanzala")
                }
            }
        }

        stage('Test') {
            steps {
                echo "Testing the code... (placeholder)"
                // Add actual test commands here
            }
        }

        stage('Push to Docker Hub') {
            steps {
                script{
                    docker_push("notes-app","latest","mohammadhanzala")
                }
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying using Docker Compose..."
                sh "docker compose up -d"
            }
        }
    }
}
