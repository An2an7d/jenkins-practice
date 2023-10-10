pipeline {
    agent { label 'AGENT-1' }
stages{
     stage('Parallel Stage') {

            parallel {
                stage('Branch A') {

                    steps {
                        echo "On Branch A"
                    }
                }
                stage('Branch B') {
                    steps {
                        echo "On Branch B"
                    }
                }
                stage('Branch C') {
                    stages {
                        stage('Nested 1') {
                            steps {
                                echo "In stage Nested 1 within Branch C"
                            }
                        }
                        stage('Nested 2') {
                            steps {
                                echo "In stage Nested 2 within Branch C"
                            }
                        }
                    }
                }
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