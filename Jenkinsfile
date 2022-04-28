pipeline {
    agent any
    tools {nodejs "Nodejs"}

    stages {
        stage('build') {
            steps {
                sh "Install package.json"
                sh "npm config ls"
            }
        }
    }
}