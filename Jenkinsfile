pipeline {
    agent {
        any { image 'node:alpine' }
    }
    stages {
        stage "Checkout repo" {
            steps {
                git 'https://github.com/othbel/project-todo-list'
            }
            
        }
        stage "List project" {
            steps {
                sh 'ls project-todo-list'
            }
            
        }
    }
}