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
                sh "sudo npm install"
                sh "sudo ng build -prod --progress=true"
            }
        }
    }
}