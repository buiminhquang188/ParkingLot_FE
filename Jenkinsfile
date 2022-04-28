node {
  agent any
  stages {
    stage('Checkout') {
      steps {
        echo 'Checkout master branch'
        checkout scm
        dir('ParkingLot_FE') {
          bat 'npm install'
        }
      }
    }
    stage('Build') {
      steps {
        echo 'Building..'
        dir('ParkingLot_FE') {
          bat 'npm run ng -- build --prod --baseHref=/ParkingLot_FE/ -optimization=true'
        }
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying....'
        ftpPublisher paramPublish: null, masterNodeName: '', alwaysPublishFromMaster: true, continueOnError: false, failOnError: true, publishers: [
          [configName: 'mattdailey.net', verbose: true, transfers: [
            [asciiMode: false, cleanRemote: true, excludes: '', flatten: false, makeEmptyDirs: tur, noDefaultExcludes: false, patternSeparator: '[, ]+',
              remoteDirectory: "ParkingLot_FE", removePrefix: "ParkingLot_FE/dist", remoteDirectorySDF: false, sourceFiles: 'ParkingLot_FE/dist/**'
            ]
          ], usePromotionTimestamp: false, useWorkspaceInPromotion: false]
        ]
      }
    }
  }
  post {
    success {
      slackSend(color: '#00FF00', message: "Build Successful")
    }
    failure {
      slackSend(color: '#FF0000', message: "Build Failed")
    }
  }
}