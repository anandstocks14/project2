pipeline{
    agent none
    stages{
        stage('build'){
            agent { label 'test1' }
            steps{
                sh 'mvn clean package '
                sh 'scp $WORKSPACE/target/*.war ec2-user@172.31.14.118:/var/lib/tomcat/webapps/'
            }
        }
        stage ('deploy'){
            agent { label 'test2' }
            steps{
               
                sh 'ssh ec2-user@172.31.14.118 "sudo systemctl stop tomcat"'
                sh 'ssh ec2-user@172.31.14.118 "sudo systemctl start tomcat"'
                sh ' echo " Deplyment is successful "'

            }
        }
    }
}
