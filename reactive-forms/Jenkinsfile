node
{
  stages {
    stage('Checkout SCM'){
  git branch: 'testAngular', url: 'https://github.com/GayathriSubb/AngularProject1.git' 
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
            steps { sh 'npm run-script test' }
        }
      }
    }

    stage('Build') {
      steps { sh 'npm run-script build' }
    }
  }
}
