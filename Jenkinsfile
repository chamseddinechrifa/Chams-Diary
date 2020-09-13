node {
        stage ('clone') {
                sh label: '', script: 'git clone "https://github.com/chamseddinechrifa/Chams-Diary.git"'
        }

        stage ('Build') {
                sh label: '', script: 'sh \'mvn compile\''
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
