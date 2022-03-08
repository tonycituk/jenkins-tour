pipeline {
    //Using a nodeJS docker container
    agent { docker { image 'node:16.13.1-alpine' } }
    stages {
        stage('test') {
            steps {
                sh 'node --version'
            }
        }
    }
}
