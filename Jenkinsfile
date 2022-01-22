pipeline {
    agent any
    tools {
        maven 'Maven'
    }

    stages {
        stage('build') {
            steps {
                //mvn test
                sh 'mvn test'
            }
        }
         stage('test') {
            steps {
                //mvn package
                sh 'mvn package'
            }
        }
         stage('deploy on test') {
            steps {
                //deploy on testing machine
                deploy adapters: [tomcat9(credentialsId: 'tomact9', path: '', url: 'http://13.127.96.135:8080')], contextPath: '/webapp', war: '**/*.war'
            }
        }
         stage('deploy on prod') {
            steps {
                //deploy on prod machine
                deploy adapters: [tomcat9(credentialsId: 'tomact9', path: '', url: 'http://13.126.30.254:8080')], contextPath: '/webapp', war: '**/*.war'
            }
        }
        
    }
}
