pipeline {
	environment {
    dockerImage = ''
  }
  agent any
    
  tools {nodejs "localnode"}
    
  stages {
        
    stage('Git') {
      steps {
        git 'https://github.com/arth20/youtube'
      }
    }
     
    stage('Build') {
      steps {
	      script{
       dockerImage = docker.build("arth20/youtube"+":$BUILD_NUMBER")
      }
      }
    }  
    stage('Deploy Image') {
      steps{
        script {
          docker.withRegistry( 'https://registry.hub.docker.com', 'dockerHub' ) {
            dockerImage.push()
          }
        }
      }
    }
	  
  }
}
