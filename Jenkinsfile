pipeline{
    agent none
    stages{
        stage('build'){
            agent { label ' test1' }
            steps{
                dir ('project2')
                sh 'mvn clean package'
                sh ' ls -lrt'
            }
        }
        stage ('deploy'){
            agent { label ' test1' }
            steps{
                sh ' echo "hello1" '
            }
        }
    }
}
