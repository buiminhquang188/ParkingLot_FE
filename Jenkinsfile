node {
    stage('Checkout SCM')
    {
        deleteDir()
        git branch: 'master', url: 'git@github.com:buiminhquang188/ParkingLot_FE.git'
    }
    stage('Install node modules'){
        sh "npm install"
    }
    stage('Build'){
       sh 'ng build --prod --aot --progress=true'
    }
    stage('Deploy')
    {
        sh 'nginx -s reload'
    }
}