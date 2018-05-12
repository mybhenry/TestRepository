pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                def userInput = input(
                 id: 'userInput', message: 'Let\'s promote?', parameters: [
                 [$class: 'TextParameterDefinition', defaultValue: 'uat', description: 'Environment', name: 'env'],
                 [$class: 'TextParameterDefinition', defaultValue: 'uat1', description: 'Target', name: 'target']
                ])
                echo ("Env: "+userInput['env'])
                echo ("Target: "+userInput['target'])
                bat 'echo "Fail!=="; exit 1'
            }
        }
    }
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
