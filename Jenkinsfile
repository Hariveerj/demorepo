pipeline {
    agent any

    stages {
        stage('Check Environment') {
            steps {
                script {
                    // Debugging: Check basic shell commands
                    sh 'echo "Checking basic shell commands"'
                    sh 'ls -la'
                }
            }
        }
        stage('Install and Check Node.js & npm') {
            steps {
                script {
                    if (isUnix()) {
                        // Debugging: Check if Node.js is already installed
                        sh '''
                        echo "Checking Node.js and npm installation status..."
                        which node || echo "Node.js not found"
                        which npm || echo "npm not found"
                        '''
                        
                        // Install Node.js and npm if not present
                        sh '''
                        if ! command -v node &> /dev/null; then
                            echo "Node.js not found. Installing..."
                            curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
                            sudo apt-get install -y nodejs
                        else
                            echo "Node.js is already installed."
                        fi

                        if ! command -v npm &> /dev/null; then
                            echo "npm not found. Installing..."
                            sudo apt-get install -y npm
                        else
                            echo "npm is already installed."
                        fi
                        '''

                        // Check versions
                        sh 'node --version'
                        sh 'npm --version'
                    } else {
                        error "Unsupported operating system"
                    }
                }
            }
        }
    }
}
