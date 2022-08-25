
pipeline {
    agent any
        stages {
             stage ('build stage') {
               steps {
                 script {
                    sh 'docker build -t my-firstpipe .'
                    sh 'docker run -it -d --name my-jenk-cont -p 8087:8080 my-firstpipe'
                    }
                  }
        }
       }
  }
