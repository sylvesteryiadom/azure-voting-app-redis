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
                    docker build -t jenkins-pipeline .
                    docker images -a
                    cd ..'''
            }
            steps {
                echo "Workspace is $WORKSPACE"
                dir("$WORKSPACE/azure-vote") {
                    script {
                    docker.withRegistry('https://hub.docker.com/', 'DockerHub') {
                    def image = docker.build("sylvesteryiadom/jenkins-course:latest")
                    image.push()
                    }
                }
            }
        }

            post{ 
                success { 
                    echo 'Docker build was successful'
                }
            }
        }
    }
    
}
