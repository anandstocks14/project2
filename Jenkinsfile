pipeline{
    agent none
    stages{
        stage('build'){
            agent { label 'test1' }
            steps{
                sh ' echo "hello" '
            }
        }
        stage ('deplo'){
            agent { label 'test1' }
            steps{
                sh ' echo "hello1 '
            }
        }
    }
}
