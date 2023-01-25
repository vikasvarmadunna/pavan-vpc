pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git branch: 'master', url: 'https://github.com/vikasvarmadunna/pavan-vpc.git'
            }
        }
        stage('create terraform infrastructre') {
            steps {
                sh 'terraform init && terraform apply -auto-approve'
            }
        }
    }
}
