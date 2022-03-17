pipeline {
    agent {
        label 'docker'
    }
    stages {
        stage('Building our image') {
            steps {
		    
                script {
                    dockerImage = docker.build ("autoia/extraction:latest", "./extraction")
                }

                script {
                   dockerImage = docker.build ("autoia/selection:latest", "./selection")
                }

                script {
                    dockerImage = docker.build ("autoia/trainig:latest", "./training")
                }
            }
        }
        
    }
}
