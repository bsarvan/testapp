pipeline {
  agent { dockerfile true }
  stages {
    
    stage('clone') {
      steps {
        echo "Cloning the repo"
        checkout scm   
        sh "pwd"
      }
    }
    
    stage('prep') {
      steps {
        echo "Executing the prep stage"
        sh 'pip install -r requirements.txt'
      }
    }
    
    stage('build') {
      steps { 
        echo "Starting the app"
        sh "./app.py"
      
      }
    }
    
    stage('test') {
      steps {
        sh 'python test.py'
      }   
    }
  }
}
