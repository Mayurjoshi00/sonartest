pipeline {
    agent any

    stages {

        stage('Compile') {
            steps {
                sh 'javac HelloWorld.java'
            }
        }

        stage('Verify SonarQube Connectivity') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    sh 'curl -s $SONAR_HOST_URL/api/system/status'
                }
            }
        }
    }
}