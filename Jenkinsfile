node{    
        stage ('clone') {
            sh 'git clone "https://github.com/chamseddinechrifa/Chams-Diary.git"'
            }
        stage ('Clean') {
            sh 'cd Chams-Diary && mvn clean'
            }
        stage ('Build') {
            agent { label 'master' }
            sh 'cd Chams-Diary && mvn compile'
            }
        stage ('Test') {
            agent any
            sh 'cd Chams-Diary && mvn test'
            }
        stage ('Package') {
            echo "pack the code"
            sh 'cd Chams-Diary && mvn package'
            }
}
