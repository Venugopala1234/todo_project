pipeline {
  agent any
  stages{
    stage("clear"){
      steps{
        sh 'rm -rf todo_project'
      }
    }
    stage("clone"){
      steps{
        sh 'git clone https://github.com/Venugopala1234/todo_project.git -b develop'
        sh 'cd todo_project'
        sh 'cp todo_project/todos/templates/todos/* /var/www/html/'
      }
    }
    stage("build"){
      steps{
        sh 'docker build -t todo .'
        sh 'docker run -d -p 8000:8000 todo'
      }
    }
    stage("deploy"){
      steps{
        sh 'docker run -d -p 8000:8000 todo'
      }
    }
  }
}

    
    
