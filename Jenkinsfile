pipeline {
        agent {
                node {
                        label 'ubuntu18-digitalocean'
                }
        }
        stages {
                stage('Install Nodejs') {
                        steps {
                                echo 'Download nodejs on NODEJS org'
                                sh 'wget https://nodejs.org/dist/v12.16.3/node-v12.16.3-linux-x64.tar.xz'
                                echo 'Extra nodejs'
                                sh 'tar xf node-v12.16.3-linux-x64.tar.xz'
                                sh 'pwd'
                                echo 'Link nodejs to /bin folder'
                                sh 'ln -s -f $(pwd)/node-v12.16.3-linux-x64/bin/node /usr/local/bin'
                                sh 'ln -s -f $(pwd)/node-v12.16.3-linux-x64/bin/npm /usr/local/bin'
                        }
                }
                stage('Build app') {
                        steps {
                                sh 'npm install'
                        }
                }
                stage('Test node') {
                        steps {
                                sh 'node --version'
                                sh 'node ./app.js & sleep 5'
                                input message: 'Checkout webapps first and then (click "Ok" to continue) '
                        }
                }
        }
}
