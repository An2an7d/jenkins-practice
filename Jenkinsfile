pipeline {
    agent { label 'AGENT-1' }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
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
            echo 'I will always run whether the job fails or success'
        }
        success { 
            echo 'I will run only when the job is succeded'
        }
        failure { 
            echo 'I will run only when the job fails'
        }
    }
}