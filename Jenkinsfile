pipeline {
     agent any
     stages {
        stage("Build") {
            steps {
                sh "npm install"
                sh "npm run build"
            }
        }
        stage("Deploy") {
            steps {
                sh "ssh -tt vagrant@192.168.21.30"
                sh "rm -rf /var/www/jenkins-react-app/*"
                sh "exit"
                sh "scp -r ${WORKSPACE}/build/* vagrant@192.168.21.30:/var/www/jenkins-react-app/"
            }
        }
    }
}
