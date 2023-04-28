pipeline {
    agent any

    stages {
        
        stage ("List project") {
            agent {
                docker {
                    image 'node:alpine'
                }
            }
            steps {
                sh 'ls project-todo-list'
            }
            
        }
    }
}