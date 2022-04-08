pipeline {
    agent {
        label 'docker'
    }
    stages {
        stage('Building our image') {
            steps {
		    
                script {
                    docker.withRegistry('https://registry.hub.docker.com/', 'dockerhub') {
                        dockerImage1 = docker.build ("autoai/evaluation:latest", "./evaluation")
                    
                        dockerImage1.push()
                    }
                }
                script {
                    dockerImage2 = docker.build ("autoai/extraction:latest", "./extraction")
                }
                script {
                   dockerImage3 = docker.build ("autoai/fusion:latest", "./fusion")
                }
                script {
                    dockerImage4 = docker.build ("autoai/imputation:latest", "./imputation")
                }
                script {
                    dockerImage5 = docker.build ("autoai/preparation:latest", "./preparation")
                }
                script {
                    dockerImage6 = docker.build ("autoai/selection:latest", "./selection")
                }
                script {
                    dockerImage7 = docker.build ("autoai/trainig:latest", "./training")
                }
                script {
                    dockerImage8 = docker.build ("autoai/validation:latest", "./validation")
                }
            }
        }
  
        
    }
}
