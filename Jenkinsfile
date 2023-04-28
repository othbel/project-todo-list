pipeline {
    agent any

    stages {
        
        stage ("Install") {
            agent {
                docker {
                    image 'node:alpine'
                    args '-p 3000:3000 -u 119:119'
                }
            }
            steps {
                sh 'npm cache clean --force '
                sh 'npm install'
            }
            
        }
        stage ("Test") {
            agent {
                docker {
                    image 'node:alpine'
                    args '-p 3000:3000'
                }
            }
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