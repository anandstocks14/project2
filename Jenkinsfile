pipeline{
    agent none
    stages{
        stage('build'){
            steps{
                dir ('project2')
                mvn clean package
                sh ' ls -lrt'
            }
        }
        stage ('deplo'){
            steps{
                sh ' echo "hello1" '
            }
        }
    }
}
