pipeline {
    agent { label 'AGENT-1' }
    options {
        timeout(time: 1, unit: 'HOURS') 
    }
    environment{
        user = 'anand'
    }
    stages {
        stage('status') {
            steps {
                sh '''
                    ls -ltr
                    pwd
                    echo "hello from github push webhook event"
                    printenv
                '''
            }
        }
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
                // error 'this is failed'
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