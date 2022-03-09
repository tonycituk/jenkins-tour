pipeline {
    //Using a nodeJS docker container
    //Check out https://www.jenkins.io/doc/book/pipeline/syntax/#agent
    agent { docker { image 'node:16.13.1-alpine' } }
    stages {
        stage('test') {
            steps {
                sh 'node --version'
            }
        }
    }
}
