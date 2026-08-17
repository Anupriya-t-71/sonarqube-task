pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git(
                    branch: 'main',
                    url: 'https://github.com/Anupriya-t-71/sonarqube-task.git'
                )
            }
        }

        stage('SonarQube Analysis') {
            environment {
                scannerHome = tool 'sonar-scanner'
            }
            steps {
                withSonarQubeEnv('SonarQube') {
                    sh """
                        ${scannerHome}/bin/sonar-scanner \
                        -Dsonar.projectKey=sonar-task \
                        -Dsonar.projectName=sonar-task \
                        -Dsonar.sources=.
                    """
                }
            }
        }
    }
}
                  
