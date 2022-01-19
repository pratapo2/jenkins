pipeline {
    agent any
    environment {
        name = "partap"
    }
    parameters {
        string(name: 'person', defaultValue: 'sourav sharma', description: 'who are you?')
        booleanParam(name: 'isMale', defaultValue: true, description: '')
        choice(name: 'City', choices: ['jaipur','Mumbai','Pune'], description: '')
    }

    stages {
        stage('Run a command') {
            steps {
                sh '''
                ls
                pwd
                '''
            }
        }
        stage('Environment variables') {
            environment {
                username = "singh"
            }
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${name}"'
                sh 'echo "${username}"'
                sh 'echo "${person}"'
            }
        }
        stage('deploy on Testing machine') {
            steps {
                sleep 1
            }
        }
        
        stage('Deploy on Prod machine') {
            steps {
                echo 'deploy on prod machine'
            }
        }
    }
    post{
        always {
            echo 'i will always say Hello again'
        }
        failure {
            echo 'i will run on failure'
        }
        success {
            echo 'i will run on success'
        }
    }
}
