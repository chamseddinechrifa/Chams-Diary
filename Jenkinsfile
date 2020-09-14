node{    
        stage ('clone') {
            echo "Pull the code from Github"
            sh 'git clone "https://github.com/chamseddinechrifa/Chams-Diary.git"'
            }
        stage ('Clean') {
            echo "Clean the code"
            sh 'cd Chams-Diary && mvn clean'
            }
       stage ('Build') {
            echo "Build the code"
            sh 'cd Chams-Diary && mvn compile'
            }
       parallel (
            node('master'){
                 stage ('Test_1') {
                                 echo "Test the code"
                                 sh 'cd Chams-Diary && mvn test'
            }
            }    
            node('Slave'){
                 stage ('Test_2') {
                                 echo "Test the code"
                                 sh 'cd Chams-Diary && mvn test'
            }
            }        
            )
        stage ('Package') {
            echo "Pack the code"
            sh 'cd Chams-Diary && mvn package'
            }
}
