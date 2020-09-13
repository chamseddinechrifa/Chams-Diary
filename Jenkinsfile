pipeline{
        agent any     
        tools { 
                maven 'Maven 3.6.3' 
                jdk 'jdk11' 
        }
        stages {
                stage ('clone') {
                     sh label: '', script: 'git clone "https://github.com/chamseddinechrifa/Chams-Diary.git"'
                }

                stage ('Build') {
                     sh 'mvn package'
                }
                stage ('Test unitaire') {
                      echo "Test the code with unit test" 
                      sh 'mvn test'
                }
                stage ('package') {
                      echo "pack the code" 
                      sh 'mvn package'
                }
   
        }

}
