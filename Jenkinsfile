pipeline {
    agent any

    stages {
        stage('Check Node.js and npm Versions') {
            steps {
                script {
                    // Check Node.js version
                    sh 'node --version'

                    // Check npm version
                    sh 'npm --version'
                }
            }
        }
    }
}
