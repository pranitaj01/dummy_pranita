pipeline{
    agent any;
    stages{
        stage('Checkout scm'){
            steps{
                checkout scm
            }
        }
        stage('Build'){
            steps{
                sh 'echo build stage'
                sh "${tool 'm3'}/bin/mvn clean compile"
            }
        }
        stage('test'){
            steps{
                sh 'echo test stage'
                sh 'mvn test'
            }
        }
        stage('Sonarqube Analysis'){
            steps{
                sh 'echo Sonarqube scanner'
                withSonarQubeEnv('sonar67'){
                    sh "${tool 'm3'}/bin/mvn sonar:sonar"
                }
            }
        }
        stage('Package'){
            steps{
                sh 'echo deploy stage'
                sh "${tool 'm3'}/bin/mvn -DskipTests"
            }
        }
        stage('Deploy stage'){
            steps{
                sh 'echo Deploy stage'
            }
        }
    }
}