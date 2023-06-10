pipeline {
    agent any

    stages {
        stage("Build") {
            steps {
                sh '''#!/bin/bash
                   ls -la
                   cat index.html
                   echo "Build by Jenkins Build# $BUILD_ID"
                '''
                echo "Build by Jenkins Build# $BUILD_ID"
            }
        }
        stage("Test") {
            steps {
                echo 'Testing..'
            }
        }
        stage("Deploy") {
            steps {
                echo 'Deploying....'
            }
        }
    }
}