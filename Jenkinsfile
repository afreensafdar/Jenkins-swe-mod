pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'rm -rf build'
                sh 'mkdir build' //create new folder
                sh 'touch build/car.txt' //create an empty file
                sh 'echo "chassis" >> build/car.txt' //put chassis inside the file
                sh 'echo "engine" >> build/car.txt' 
                sh 'echo "body" >> build/car.txt' 
            }
        }
            stage('Test') {
          steps {
              sh 'test -f build/car.txt'
              sh 'grep "chassis" build/car.txt'
              sh 'grep "engine" build/car.txt'
              sh 'grep "body" build/car.txt'
          }
     
        }
        stage('Publish') {
          steps {
              archiveArtifacts artifacts: 'build/'
          }
     
        }
    }
}
