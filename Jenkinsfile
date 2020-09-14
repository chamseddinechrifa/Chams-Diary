pipeline {
  agent any
  stages {
    stage('clone') {
      steps {
          echo "Pull the code from Github"
          sh 'git clone "https://github.com/chamseddinechrifa/Chams-Diary.git"'
            }
    }
    stage ('Clean') {
      steps {      
            echo "Clean the code"
            sh 'cd Chams-Diary && mvn clean'
            }
      }
    stage ('Build') {
      steps {      
            echo "Build the code"
            sh 'cd Chams-Diary && mvn compile'
            }
      }
    stage('Run Tests') {
            parallel {
                stage('Test 1') {
                    steps {
                                 echo "Test the code on master"
                                 sh 'cd Chams-Diary && mvn test'
                    }
                }
                stage('Test 2') {
                    steps {
                                echo "Test the code on slave"
                                sh 'cd Chams-Diary && mvn test'
                    }
                }
            }
            }
    stage ('Package') {
      steps {      
            echo "Pack the code"
            sh 'cd Chams-Diary && mvn package'
            }
      }

    }

}
