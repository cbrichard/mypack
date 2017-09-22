pipeline {
    agent any
    
    environment {
    AWS_ACCESS_KEY_ID     = credentials('AWS_ACCESS_KEY_ID')
    AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
    }

    stage('Clone repository') {
        /* Let's make sure we have the repository cloned to our workspace */

        checkout scm
    }

    stage('Validate Template') {
        sh('packer validate base-ami.json')
    }

    stage('Build Image') {
        sh('packer build base-ami.json')
        }
}

