node {
    def app

    stage('Clone repository') {
        /* Let's make sure we have the repository cloned to our workspace */

        checkout scm
    }

    stage('Validate Template') {
        sh('packer validate centos-ami.json')
    }

    stage('Build Image') {
        sh('packer build centos-ami.json')
        }
}

