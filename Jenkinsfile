pipeline {
    agent any

    stages {
        stage('Check PATH') {
            steps {
                sh 'echo $PATH'
            }
        }
        stage('Check Node.js and npm Versions') {
            steps {
                sh 'node --version'
                sh 'npm --version'
            }
        }
    }
}
