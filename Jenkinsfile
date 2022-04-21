pipeline {
    agent any

    stages {
        stage('Verify Branch') {
            steps {
                echo "$GIT_BRANCH"
            }
        }

        stage('Docker build') {
            steps {
                sh '''
                    cd azure-vote/
                    docker build -t jenkins-pipeline .
                    docker images -a
                    cd ..'''
            }
        }
        stage('Container push') {
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
                post{ 
                    success { 
                        echo 'Successfully pushed to repository'
                    }
                }
            }   
        }

    }
    
}
