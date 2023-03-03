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
                sh "ssh vagrant@192.168.21.30 \"rm -rf /var/www/jenkins-react-app/*\""
                sh "scp -r ${WORKSPACE}/build/* vagrant@192.168.21.30:/var/www/jenkins-react-app/"
            }
        }
    }
}
