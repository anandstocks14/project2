pipeline{
    agent none
    stages{
        agent { label 'test1' }
        stage('build'){
            steps{
                sh 'mvn clean package '
                
            }
        }
        stage ('deploy'){
            agent { label 'test2' }
            steps{
                sh ' sudo scp /home/ec2-user/workspace/project2/target/*.war ec2-user@172.31.14.118://var/lib/tomcat/webapps/'
                sh ' sudo systemctl stop tomcat '
                sh ' sudo systemctl start tomcat '
                sh ' echo " Deplyment is successful "

            }
        }
    }
}
