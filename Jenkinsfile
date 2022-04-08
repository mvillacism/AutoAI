pipeline {
    agent {
        label 'docker'
    }
    stages {
        stage('Building and deploy images') {
            steps {
		    
                script {
                    dockerImage = docker.build ("autoaiproject/evaluation:latest", "./evaluation")
                    docker.withRegistry('', 'dockerhub') {
                        dockerImage.push()
                    }
    
            
                    dockerImage = docker.build ("autoaiproject/extraction:latest", "./extraction")
                    docker.withRegistry('', 'dockerhub') {
                        dockerImage.push()
                    }
            
                    dockerImage = docker.build ("autoaiproject/fusion:latest", "./fusion")
                    docker.withRegistry('', 'dockerhub') {
                        dockerImage.push()
                    }
               
                    dockerImage = docker.build ("autoaiproject/imputation:latest", "./imputation")
                    docker.withRegistry('', 'dockerhub') {
                        dockerImage.push()
                    }
                
                    dockerImage = docker.build ("autoaiproject/preparation:latest", "./preparation")
                    docker.withRegistry('', 'dockerhub') {
                        dockerImage.push()
                    }
                   
                    dockerImage = docker.build ("autoaiproject/selection:latest", "./selection")
                    docker.withRegistry('', 'dockerhub') {
                        dockerImage.push()
                    }
                
                
                    dockerImage = docker.build ("autoaiproject/trainig:latest", "./training")
                    docker.withRegistry('', 'dockerhub') {
                        dockerImage.push()
                    }
               
                    dockerImage = docker.build ("autoaiproject/validation:latest", "./validation")
                    docker.withRegistry('', 'dockerhub') {
                        dockerImage.push()
                    }
                }
            }
        }
        
    }
}
