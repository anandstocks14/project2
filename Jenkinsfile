pipeline{
    agent none
    stages{
        stage('build'){
            agent { label 'node1' }
            steps{
                sh ' echo "hello" '
            }
        }
        stage ('deplo'){
            agent { label 'node1' }
            steps{
                sh ' echo "hello1 '
            }
        }
    }
}
