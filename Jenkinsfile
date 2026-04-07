pipeline {
    agent any

    stages {

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
