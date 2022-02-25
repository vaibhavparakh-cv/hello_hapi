#!/usr/bin/env groovy

pipeline {

    agent {
        docker {
            image 'node'
            args '-u root'
        }
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'npm install'
                sh 'git merge --abort; git rebase --abort; git clean -fd; git checkout .; BR=$(git branch --show-current); git checkout master; git branch -D $BR; git pull; git checkout $BR;'
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
