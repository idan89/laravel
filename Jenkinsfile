node('php'){
    stage('Clean'){
        deleteDir()
        sh 'ls -la'
    }
    
    stage('Fetch') {
        checkout scm
    }
    
    stage('Docker Build') {
        sh 'docker build -t convisodarenas/laravel:$BUILD_NUMBER .'
    }
    
    stage('Docker Ship') {
        sh 'docker push convisodarenas/laravel:$BUILD_NUMBER'
        sh 'docker rmi -f convisodarenas/laravel:$BUILD_NUMBER'
    }
}
