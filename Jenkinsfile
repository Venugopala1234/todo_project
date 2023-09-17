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
        sh "cd todo_project/"
      }
    }
    stage("copy"){
      steps{
        echo "copy file"
        sh "cp -r todo_project/todos/templates/todos/* /var/www/html/"
      }
    }
    stage("build"){
      steps{
        echo "build"
       script {
                    dockerImage = docker.build('todo')
                }
      }
    }
    stage("deploy"){
      steps{
        echo "deploy"
        script {
                    dockerImage.inside('-p 8080:80 --name DOCKER_CONTAINER_NAME') 
                    }
      }
    }
  }
}
    
