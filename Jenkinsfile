pipeline {
    agent none

    stages {
        stage('Build') {
            agent { label 'test1' }
            steps {
                sh 'mvn clean package'
                sh 'scp target/tomcat-demo.war ec2-user@172.31.14.118:/home/ec2-user/'
            }
        }

        stage('Deploy') {
            agent { label 'test2' }
            steps {
                sh 'sudo mv /home/ec2-user/tomcat-demo.war /var/lib/tomcat/webapps/'
                sh 'sudo systemctl restart tomcat'
                sh 'echo "Deployment is successful"'
            }
        }
    }
}
