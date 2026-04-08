pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/bhavyasri1010/bhavyasri-war.git'
            }
        }

        stage('Build WAR') {
            steps {
                sh '''
                    cd /home/user/CalculatorApplicationWAR
                    mvn clean package

                    # Copy WAR to workspace
                    cp target/*.war $WORKSPACE/
                '''
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: '*.war'
        }
    }
}
