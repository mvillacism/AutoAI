pipeline {
    agent {
        label 'docker'
    }
    stages {
        stage('Building our image') {
            steps {
		    
                script {
                    dockerImage = docker.build ("autoai/evaluation:latest", "./evaluation")
                }
                script {
                    dockerImage = docker.build ("autoai/extraction:latest", "./extraction")
                }
                script {
                   dockerImage = docker.build ("autoai/fusion:latest", "./fusion")
                }
                script {
                    dockerImage = docker.build ("autoai/imputation:latest", "./imputation")
                }
                script {
                    dockerImage = docker.build ("autoai/preparation:latest", "./preparation")
                }
                script {
                    dockerImage = docker.build ("autoai/selection:latest", "./selection")
                }
                script {
                    dockerImage = docker.build ("autoai/trainig:latest", "./training")
                }
                script {
                    dockerImage = docker.build ("autoai/validation:latest", "./validation")
                }
            }
        }
        
    }
}
