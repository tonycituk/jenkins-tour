pipeline {
    agent { docker { image 'alpine:latest' } }
    stages {
        stage('build') {
            steps {
                sh 'echo "Hello World!"'
            }
        }
    }
}
