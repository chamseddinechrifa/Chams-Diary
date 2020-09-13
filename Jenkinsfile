node {
        stage ('clone') {
                sh label: '', script: 'git clone "https://github.com/chamseddinechrifa/Chams-Diary.git"'
        }

        stage ('Build') {
                def mvnHome = tool name: 'maven-3' , type: 'maven' 
                sh "${mvnHome}/bin/mvn package"
        }
}
