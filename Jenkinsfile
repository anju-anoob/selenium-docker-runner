pipeline{
    agent any
    stages{
        stage("Start Grid"){
            steps{
                sh "docker-compose up -d hub chrome firefox --no-color"
            }
        }
        stage("Start Modules")
            steps{
                sh "docker-compose up search-module book-flight-module --no-color"
            }
        }
        stage("Bring down grid"){
            steps{
                sh "docker-compose down"
            }
        }
    }
}