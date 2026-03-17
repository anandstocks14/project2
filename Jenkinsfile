pipeline{
    agent none
    stages{
        stage('build'){
            agent { label 'test1' }
            steps{
                sh 'mvn clean package '
                sh 'scp target/tomcat-demo.war ec2-user@172.31.14.118:/home/ec2-user/'
            }
        }
        stage ('deploy'){
            agent { label 'test2' }
            steps{
                sh 'ssh ec2-user@172.31.14.118 "sudo mv /home/ec2-user/tomcat-demo.war /var/lib/tomcat/webapps"'
                sh 'ssh ec2-user@172.31.14.118 "sudo systemctl stop tomcat"'
                sh 'ssh ec2-user@172.31.14.118 "sudo systemctl start tomcat"'
                sh ' echo " Deplyment is successful "'

            }
        }
    }
}
