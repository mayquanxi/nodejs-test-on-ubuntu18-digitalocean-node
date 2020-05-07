pipeline {
        agent {
              docker {
                    image 'node:13'
                    args '-p 3000:3000'
              }
        }
        stages {
              stage('build') {
                    steps {
                         echo 'check version nodejs:'
                         sh 'node --version'
                    }
              }
              stage('Test code') {
                    steps {
                         timeout(time:1, unit:'MINUTES') {
                                 sh 'node ./app.js'
                         }
                    }     
              }
        }
}
