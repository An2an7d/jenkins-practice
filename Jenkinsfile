pipeline {
    agent { label 'AGENT-1' }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    triggers{
        cron('*****')
    }
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
        stage('SSH Username') {
        environment {
             SSH_CREDS = credentials('ssh-auth')
                }
                steps{
                    sh 'printenv'
                }
        }
        stage('params') {
            steps {
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
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