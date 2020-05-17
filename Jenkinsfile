pipeline {
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
        sh 'npm install'
	sh 'npm run build'
      }
    }  
    
  }
}
