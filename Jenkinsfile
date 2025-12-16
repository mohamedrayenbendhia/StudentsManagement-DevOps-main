cat <<EOL > Jenkinsfile
pipeline {
    agent any

    tools {
        jdk 'JAVA_HOME'
        maven 'M2_HOME'
    }

    environment {
        GIT_CREDENTIALS = credentials('GITT')
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/mohamedrayenbendhia/StudentsManagement-DevOps-main.git',
                    credentialsId: 'GITT'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
EOL
