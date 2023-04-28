pipeline {
    agent any

    stages {
        
        stage ("List project") {
            agent {
                docker {
                    image 'node:alpine'
                    args '-p 3000:3000'
                }
            }
            steps {
                sh 'ls project-todo-list'
            }
            
        }
    }
}