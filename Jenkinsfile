pipeline {
    agent {
        docker { image 'node:alpine' }
    }
    stages {
        stage "Checkout repo" {
            git 'https://github.com/othbel/project-todo-list'
        }
        stage {
            sh 'ls project-todo-list'
        }
    }
}