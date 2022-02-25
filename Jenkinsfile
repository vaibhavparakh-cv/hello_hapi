#!/usr/bin/env groovy

pipeline {

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'npm test'
                sh 'git clean -fd; git checkout .; BR=$(git branch --show-current); git checkout master; git branch -D $BR; git pull; git checkout $BR;'
            }
        }
    }
}
