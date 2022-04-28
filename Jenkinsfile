pipeline {
    agent any
    tools {nodejs "Nodejs"}
    
    environment {
        HOME = '.'
    }
    
    stages {
        stage('build') {
            steps {
                echo "Install package.json"
                sh "npm install"
                sh "ng build -prod --progress=true"
            }
        }
    }
}