// pipeline {
//     agent any

//     stages {
//         stage('Verify Branch') {
//             steps {
//                 echo "$GIT_BRANCH"
//             }
//         }

//         stage('Docker build') {
//             steps {
//                 sh '''
//                     cd azure-vote/ 
//                     docker build -t jenkins-pipeline .
//                     docker images -a
//                     cd ..'''
//             }
//         }
//         stage('Container push') {
//             steps {
//                     echo "Workspace is $WORKSPACE"
//                     sh ''' cd azure-vote/ '''
//                         script {
//                         docker.withRegistry('https://hub.docker.com/', 'DockerHub') {
//                         def image = docker.build("sylvesteryiadom/jenkins-course:latest")
//                         image.push()
//                         }
//                     }
                
//                 post{ 
//                     success { 
//                         echo 'Successfully pushed to repository'
//                     }
//                 }
//             }   
//         }

//     }
    
// }
// node{
//     stage("Echo on master"){
//         if(env.BRANCH_NAME == 'master'){
//             echo "This is the master branch"
//         }else{
//             echo "This is NOT the master branch"
//         }
//     }
// }

pipeline {
    agent any 
        stages {
            stage('Stage 1 - compiling code') {
                
                steps {
                echo "Compiling the code from SCM "
                }
        }
                    stage('Stage 2 - testing code') {
                
                steps {
                echo "Testing the code now "
                }
        }
                    stage('Stage 3 - Deploying the code') {
                
                steps {
                 echo "Deploying the code to MASTER "
                }
        }
    }
}