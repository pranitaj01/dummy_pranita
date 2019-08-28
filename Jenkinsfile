pipeline{
    agent any
    stages{
        stages('Sonarqube Analysis'){
            steps{
                sh 'echo Sonarqube Analysis'
            }
        }
        stages('Build'){
            steps{
                sh 'build stage'
            }
        }
        stages('test'){
            steps{
                sh 'test stage'
            }
        }
        stages('deploy'){
            steps{
                sh 'deploy stage'
            }
        }
    }
}