pipeline {
    agent any

    options {
        ansiColor('xterm')
        timeout(time: 240, unit: 'SECONDS')
        timestamps()
    }

    stages {
        stage('Stage 1 - Git fetch') {
            steps {
                git branch: 'mavenWrapper', url: 'https://github.com/radzwin/junit4.git'
            }
        }

        stage('Stare 2 - Maven') {
            steps {
                sh "./mvnw clean install"
            }
        }

        stage('Stare 3 - Test') {
            steps {
                junit '**/target/surefire-reports/*.xml'
            }
        }
    }
}