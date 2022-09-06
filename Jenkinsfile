#!groovy

properties([disableConcurrentBuilds()])

pipeline {
    agent any

    options {
        buildDiscarder(logRotator(numToKeepStr: '10', artifactNumToKeepStr: '10'))
        timestamps()
    }
    stages {
        stage("create docker image") {
            steps {
                echo " ============== start building image ==================="
                dir ('docker/toolbox') {
                	sh 'docker build -t slavik/toolbox:latest . '
                    sh "python --version"
                }
            }
        }
   }
}