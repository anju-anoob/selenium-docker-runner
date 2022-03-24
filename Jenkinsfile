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
    }
    post{
        always{
            archiveArtifacts artifacts: 'output/**'
            sh "docker-compose down"
        }
    }
}