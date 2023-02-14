pipeline {
    agent any 
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('image build') {
            steps {
                sh 'docker image build -t krishna123123/test1:1.0 .'
            }
        }
        stage('image push') {
            steps {
                sh 'docker image push krishna123123/test1:1.0'
            }
        }
        stage('deploy') {
            steps {
                sh 'kubectl apply -f deploy.yml'
            }
        }
    }
}
