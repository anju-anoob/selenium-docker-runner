pipeline{
    agent any
    stages{
        stage("Pull latest image"){
            steps{
                sh "docker pull anjuabraham/selenium-maven-docker"
            }
        }
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