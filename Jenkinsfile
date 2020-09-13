node{    
        tools { 
            maven 'Maven 3.6.3'
            jdk 'JDK 9.0.4'
        }
        stage ('clone') {
            sh 'git clone "https://github.com/chamseddinechrifa/Chams-Diary.git"'
            }
        stage ('Clean') {
            sh 'cd Chams-Diary && mvn clean'
            }
        stage ('Build') {
            sh 'cd Chams-Diary && mvn compile'
            }
        stage ('Test') {
            sh 'cd Chams-Diary && mvn test'
            }
        stage ('Package') {
            echo "pack the code"
            sh 'cd Chams-Diary && mvn package'
            }
        

}
