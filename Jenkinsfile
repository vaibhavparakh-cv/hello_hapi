#!/usr/bin/env groovy

pipeline {
    agent any
        stages {
            stage('Build') {
                steps {
                    echo 'Building...'
                    sh 'git merge --abort; git rebase --abort; git clean -fd; git checkout .'
                }
            }
        }
}