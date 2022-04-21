pipeline {
    agent any

    stages {
        stage('Verify Branch') {
            steps {
                echo "$GIT_BRANCH"
            }
        }

        stage('Docker Build') {
            steps {
                sh 'sudo docker images -a'
                sh '''cd azure-vote/
                    sudo docker build -t jenkins-pipeline .
                    sudo docker images -a
                    cd ..'''
            }
        }
    }
    
}
