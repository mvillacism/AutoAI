pipeline {
    agent {
        label 'docker'
    }
    stages {
        stage('Building images') {
            steps {
		    
                script {
                    dockerImage1 = docker.build ("autoaiproject/evaluation:latest", "./evaluation")
                }
                script {
                    dockerImage2 = docker.build ("autoaiproject/extraction:latest", "./extraction")
                }
                script {
                   dockerImage3 = docker.build ("autoaiproject/fusion:latest", "./fusion")
                }
                script {
                    dockerImage4 = docker.build ("autoaiproject/imputation:latest", "./imputation")
                }
                script {
                    dockerImage5 = docker.build ("autoaiproject/preparation:latest", "./preparation")
                }
                script {
                    dockerImage6 = docker.build ("autoaiproject/selection:latest", "./selection")
                }
                script {
                    dockerImage7 = docker.build ("autoaiproject/trainig:latest", "./training")
                }
                script {
                    dockerImage8 = docker.build ("autoaiproject/validation:latest", "./validation")
                }
            }
        }
        stage('Deploy docker images'){
            steps {
                script {
                    docker.withRegistry('', 'dockerhub') {
                        dockerImage1.push()
                        dockerImage2.push()
                        dockerImage3.push()
                        dockerImage4.push()
                        dockerImage5.push()
                        dockerImage6.push()
                        dockerImage7.push()
                        dockerImage8.push()
                    }

                }

            }

        }
  
        
    }
}
