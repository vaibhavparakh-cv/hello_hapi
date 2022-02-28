#!/usr/bin/env groovy

pipeline {
    agent any
        stages {
            stage('Build') {
                steps {
                    echo 'Building...'
                    sh 'git clean -fd ; git checkout . ; git reset --hard ; git checkout master; git pull origin master; git branch -D $Branch; git fetch; git checkout $Branch; git pull;'
                }
            }
        }
}