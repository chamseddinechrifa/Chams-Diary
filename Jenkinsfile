pipeline {
  agent none
  stages {
    stage('clone') {
      agent {
        label 'master'
      }
      steps {
          echo "Pull the code from Github"
          sh 'git clone "https://github.com/chamseddinechrifa/Chams-Diary.git"'
            }
    }
    stage ('Clean') {
      agent {
        label 'master'
      }
      steps {      
            echo "Clean the code"
            sh 'cd Chams-Diary && mvn clean'
            }
      }
    stage ('Build') {
      agent {
        label 'master'
      }
      steps {      
            echo "Build the code"
            sh 'cd Chams-Diary && mvn compile'
            }
      }
    stage('Run Tests') {
            parallel {
                stage('Test On master') {
                    agent {
                        label 'master'
                    }
                    steps {
                                 echo "Test the code on master"
                                 sh 'cd Chams-Diary && mvn test'
                    }
                }
                stage('Test On slave') {
                    agent {
                        label 'slave'
                    }
                    steps {
                                echo "Test the code on slave"
                                sh 'cd /var/lib/jenkins/workspace/Chams-Diary pipeline/Chams-Diary && mvn test'
                    }

                }
            }
            }
    stage ('Package') {
      agent {
        label 'master'
      }
      steps {      
            echo "Pack the code"
            sh 'cd Chams-Diary && mvn package'
            }
      }

    }

}
