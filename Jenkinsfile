pipeline
{
agent any
tools{
nodejs "nodejs"
}
  stages {
    stage('Clean'){
steps
      {sh 'npm clean'}
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
