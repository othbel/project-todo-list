pipeline {
    agent any

    stages {
        stage ("Checkout repo") {
            agent {
                docker {
                    image 'node:alpine'
                }
            }
            steps {
                git 'https://github.com/othbel/project-todo-list'
            }
            
        }
        stage ("List project") {
            steps {
                sh 'ls project-todo-list'
            }
            
        }
    }
}