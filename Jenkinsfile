pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                
                echo ("DEPLOY_ENV: "+DEPLOY_ENV)
                bat 'echo "Fail!=="; exit 1'
            }
        }
    }
    properties([
                  parameters([
                    string(name: 'DEPLOY_ENV', defaultValue: 'TESTING', description: 'The target environment', )
                   ])
                ])
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
