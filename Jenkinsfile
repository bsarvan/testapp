pipeline {
  agent any
  stages {
    stage('prep') {
      steps {
        echo "Skipping the prep stage"
      }
    }
    
    stage('build') {
      steps {
        echo "Cloning the repo"
        checkout scm   
        sh "pwd"
        
        dir("testapp") {
          sh "pwd"
          echo "Starting the app"
          sh "./app.py"
        }
      }
    }
    
    stage('test') {
      steps {
        sh 'python test.py'
      }   
    }
  }
}
