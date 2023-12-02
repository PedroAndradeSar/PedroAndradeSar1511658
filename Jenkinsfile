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
                //docker --version
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
            }
        }
    }
}

//tem que fazer rodar esses testes
    // "test:e2e": "cross-env NODE_ENV=test cypress open",
    // "test:ci": "cross-env NODE_ENV=test cypress run",
    // "test": "node node_modules/grunt-cli/bin/grunt test",