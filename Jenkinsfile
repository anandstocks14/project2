pipeline {
    agent any
    stages {
        stage('Build') {
            
            steps {
                sh 'mvn clean package'
            }
        }
    }
    post {
            always {
                script {
                    currentBuild.description = "Build #${env.BUILD_NUMBER} | ${currentBuild.currentResult}"
                }
            }
    }
        
            
}
