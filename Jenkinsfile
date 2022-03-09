// Using environment variables
pipeline {
    //Using a nodeJS docker container
    agent { docker { image 'alpine:latest' } }
    environment {
        DISABLE_AUTH = 'true'
        DB_ENGINE = 'sqlite'
    }
    stages {
        stage('build') {
            steps {
                echo "Database engine is ${DB_ENGINE}"
                echo "DISABLE_AUTH is ${DISABLE_AUTH}"
                sh 'printenv'
            }
        }
    }
}
