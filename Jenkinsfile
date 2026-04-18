pipeline{
    agent { label 'AGENT-1'}
    stages{
        stage('Build'){
            steps{
                script{
                sh """
                echo "hello,this is build"
                """
                }
            }
        }
        stage('Test'){
            steps{
                script{
                sh """
                echo "hello,this is Test"
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