pipeline {
    agent {
        label 'ansible'
    }
    stages {
        stage('Clear work dir') {
            steps {
                deleteDir()
            }
        }
        stage('Clone git repo') {
            steps {
                dir('vector-role') {
                git branch: 'main', url: 'https://github.com/kibernetiq/vector-role.git'
                }
            }
        }
        stage('Molecule test') {
            steps {
                dir('vector-role') {
                sh 'molecule test'
                }
            }
        }
    }
}