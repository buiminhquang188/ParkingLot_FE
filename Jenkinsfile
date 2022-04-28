pipeline {
    agent any
    tools {nodejs "nodejs"}

    stages {
        stage('build') {
            steps {
                sh "Install package.json"
                sh "npm config ls"
            }
        }
    }
}