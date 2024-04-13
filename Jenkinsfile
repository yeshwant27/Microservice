wapipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') { 
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker build -t yeshwant27/checkoutservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker push yeshwant27/checkoutservice:latest "
                    }
                }
            }
        }
    }
}
