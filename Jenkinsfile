pipeline {
  agent any
  stages{
    stage("clear"){
      steps{
        sh 'rm -rf todo_project'
        sh 'git clone https://github.com/Venugopala1234/todo_project.git -b develop'
        sh 'cd todo_project'
        sh 'docker build -t todo .'
        sh 'docker run -d -p 8000:8000 todo'
      }
    }
  }
}
    
