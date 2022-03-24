pipeline{
    agent any
    stages{
        stage("Start Grid"){
            steps{
                sh "docker-compose up -d hub chrome firefox"
            }
        }
        stage("Start Modules"){
            steps{
                sh "docker-compose up search-module book-flight-module"
            }
        }
        stage("Bring down grid"){
            steps{
                sh "docker-compose down"
            }
        }
    }
}