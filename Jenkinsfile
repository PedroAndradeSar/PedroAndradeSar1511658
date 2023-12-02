pipeline {
    agent any
    tools{nodejs 'nodejs'}
    stages {
        stage('Start NodeGoat') {
            steps {
                sh '''
                        npm install
                '''
            }
        }
        stage('Test NPM') {
            steps {
                sh '''
                    npm test
                '''
            }
        }

        stage('Build') {
            steps {
                
                sh '''
                    docker-compose build
                '''
                
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'

                sh'npm install'
                sh'npm test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'

                 sh'docker-compose up'
            }
        }
    }
}

