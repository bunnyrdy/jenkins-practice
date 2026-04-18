pipeline{
    agent { label 'AGENT-1'}
    environment {
        PROJECT = 'EXPENSE'
        COMPONENT = 'BACKEND'
        DEPLOY_TO = 'TEST'
    }
    options {
        disableConcurrentBuilds()
        timeout(time: 30, unit:'MINUTES')
    }
    parameters {
        string(name: 'STATEMENT', defaultValue: 'hello; ls /', description: 'What should I say?')
    }
    stages{
        stage('Build'){
            steps{
                script{
                sh """
                echo "hello,this is build"
                echo "project: $PROJECT"
                sleep 15
                """
                }
            }
        }
        stage('Test'){
            steps{
                script{
                sh """
                echo "hello,this is Test"
                echo "${STATEMENT}"
                """
                }
            }
        }
         stage('Deploy'){
            steps{
                script{
                sh """
                echo "hello,this is deploy"
                """
                }
            }
        }
        
    }

    post {
            always {
                echo 'i will run if it is success or fail'
            }
            failure {
                echo 'i will run when pipeline fails'
            }
            success {
                echo 'i will run when pipeline success'
            }
        }

}