pipeline {
     agent any
     stages {
        stage("Build") {
            steps {
                sh "sudo npm install"
                sh "sudo npm run build"
            }
        }
        stage("Deploy") {
            steps {
                sh "ssh vagrant@192.168.21.30"
                sh "sudo rm -rf /var/www/jenkins-react-app"
                sh "exit"
                sh "scp -r ${WORKSPACE}/build/ /var/www/jenkins-react-app/"
            }
        }
    }
}
