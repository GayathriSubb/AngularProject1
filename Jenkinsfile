pipeline
{
  agent any
  tools {
	nodejs "nodejs"
	}
  stages {
    
    
    stage('Install') {
      steps { sh 'npm install' }
    }

    stage('Test') {
      
        stage('Unit tests') {
            steps { sh 'npm test' }
        }
      
    }
 
    stage('Build') {
      steps { sh 'npm build' }
    }
  }
}
