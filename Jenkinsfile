pipeline {
    agent any 
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('image build') {
            steps {
                sh 'docker image build -t krishna8080/test1:1.0 .'
            }
        }
        stage('image push') {
            steps {
                sh 'docker image push krishna8080/test1:1.0'
            }
        }
        stage('deploy') {
            steps {
                sh 'kubectl apply -f deploy.yml'
            }
        }
    }
}
