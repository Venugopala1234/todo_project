pipeline {
  agent any
  stages{
    stage("clear"){
      steps{
        echo "clean"
        sh "rm -rf *"
      }
    }
    stage("clone"){
      steps{
        echo "cloning the code"
        sh "git clone -b develop https://github.com/Venugopala1234/todo_project.git"
        cd todo_project/
      }
    }
    stage("copy"){
      steps{
        echo "copy file"
        sh "cp -r todos/templates/todos/* /var/www/html/"
      }
    }
    stage("build"){
      steps{
        echo "build"
        sh "docker build -t todo ."
      }
    }
    stage("deploy"){
      stpes{
        echo "deploy"
        sh "docker run -d -p 8000:8000 todo"
      }
    }
  }
}
    
