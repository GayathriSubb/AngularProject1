pipeline
{
agent any
tools{
nodejs "nodejs"
}
  stages {
    
    stage('Checkout SCM'){
  git branch: 'main', credentialsId: '43afff5e-4eee-4bc1-a348-7dbabb598ae3', url: 'https://github.com/GayathriSubb/AngularProject1.git' 
  }
    stage('Install') {
      steps { sh 'npm install' }
    }

    stage('Test') {
      parallel {
        stage('Static code analysis') {
            steps { sh 'npm run-script lint' }
        }
        stage('Unit tests') {
            steps { sh 'npm test' }
        }
      }
    }

    stage('Build') {
      steps { sh 'npm build' }
    }
  }
}
