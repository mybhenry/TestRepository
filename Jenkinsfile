pipeline {
    agent any
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        
    }
    stages {
        stage('Example') {
            steps {
                echo "--- Running ${env.BUILD_ID} on ${env.JENKINS_URL} " 
                bat 'echo sdfsdf88888888888 >> sdagrhrty4fgdabc000.txt' 
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
                archiveArtifacts artifacts: 'README.md,zxcZXZXcasdfe.xml', fingerprint: true, onlyIfSuccessful: true
            }
        }
        stage('Test') {
            steps {                
                echo ("PERSON:--- ${params.PERSON} ")
                bat 'echo "Fail!=="; exit 1'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
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
