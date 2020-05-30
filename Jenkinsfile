bool whateverFunction() {
    sh 'ls /'
    return true
}

pipeline {
  agent any
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
        def result = whateverFunction()
        echo "Printing the result ${result}"  
        echo "Executing the prep stage"
        sh 'pip3 install -r requirements.txt'
      }
    }
    
    stage('build') {
      steps { 
        echo "Starting the app"
        sh "./app.py &"
      
      }
    }
    
    stage('test') {
      steps {
        sh 'python test.py'
      }   
    }
  }
}
