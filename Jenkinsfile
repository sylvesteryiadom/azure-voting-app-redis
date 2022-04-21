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
                sh '''
                    cd azure-vote/
                    sudo docker build -t jenkins-pipeline .
                    docker images -a
                    cd ..'''
            }
        }
    }
    
}
