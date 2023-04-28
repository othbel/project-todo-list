pipeline {
    agent {
        docker {
                image 'node:alpine'
                args '-p 3000:3000'
        }
    }

    stages {
        stage ("Install") {        
            steps {
                sh 'npm cache clean --force '
                sh 'chown -R 114:119 "~/.npm"'
                sh 'npm install'
            }
        }
        stage ("Test") {
            steps {
                sh 'npm test'
            }
        }
        stage ("Build") {
            agent any
            steps {
                sh 'docker build -t othbel/todo-list-app .'
            }
        }
    }
}