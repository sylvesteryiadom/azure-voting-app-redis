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
            stage('starting') {
                // when {}
                steps {
                echo "Declarative branch"
                }
        }
    }
}