pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/bhavyasri1010/bhavyasri-jar.git'
            }
        }

        stage('Build WAR') {
            steps {
                sh '''
                    mvn clean package

                    # Copy WAR to workspace (optional, already in workspace)
                    cp target/*.war $WORKSPACE/
                '''
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: 'target/*.war'
        }
    }
}
