pipeline {
    agent any

    stages {
        // stage ("Install") {        
        //     steps {
        //         sh 'npm cache clean --force '
        //         // sh 'chown -R 114:119 "~/.npm"'
        //         echo "${env.USER}"
        //         echo "${env.HOME}"
        //         sh 'ls -laR /var/lib/jenkins/workspace'
        //         sh 'rm -r node_modules'
        //         sh 'npm install --loglevel=verbose'
        //     }
        // }
        // stage ("Test") {
        //     steps {
        //         sh 'npm test'
        //     }
        // }
        stage ("Docker Build") {
            agent any
            steps {
                sh 'docker build -t othbel/todo-list-app .'
            }
        }
        stage ("Docker Push") {
            agent any
            steps {
                withCredentials([usernamePassword(credentialsId: 'Docker Hub Creds', passwordVariable: 'passwordHub', usernameVariable: 'userHub')]) {
                    sh "docker login -u ${env.userHub} -p ${env.passwordHub}"
                    sh "docker push othbel/todo-list-app:latest"
                }
            }
        }
    }
}