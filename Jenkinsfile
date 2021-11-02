pipeline {

    agent any
    tools {
        
    }

    stages {
        
        stage("build") {
            
            steps {
                sh '''
                    npm --version
                    npm config set spin false'
                    export DISPLAY=:1.0
                    sh -e /etc/init.d/xvfb start
                    sleep 3
                '''
                sh '''
                    npm install -g yarn
                    gem install compass
                    cd ui && yarn
                    cat npm-debug.log || true
                '''
                sh 'yarn ci'


            }
        }

        stage("deploy") {
            
            steps{
                echo 'Deploy project to the server'
            }
        }

    }
}
