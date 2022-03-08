pipeline {
    agent { docker { image 'alpine:latest' } }
    stages {
        stage('build') {
            steps {
                sh 'echo "Hello World!"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                  '''
                //retry step until succesful or 3 attempts failed
                retry(3) {
                    sh 'this will not work'
                }
                //Waits 3 minutes, if step does not complete
                //pipeline will be marked as failed.
                timeout(time: 3, unit: 'MINUTES'){
                    sh 'this should not work too'
                }
            }
        }
    }
    /*
    When the Pipeline has finished executing,
    you may need to run clean-up steps or perform some actions based on the outcome
    of the Pipeline. These actions can be performed in the post section.
    */
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}
