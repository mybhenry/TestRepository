pipeline {
    agent any
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        int(name: 'PERSON', defaultValue: 45, description: 'Who should I say hello to?')
        boolean(name: 'PERSON', defaultValue: false, description: 'Who should I say hello to?')
        date(name: 'PERSON',  description: 'Who should I say hello to?')
    }
    stages {
        stage('Test') {
            steps {
                
                echo ("PERSON: "+PERSON)
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
