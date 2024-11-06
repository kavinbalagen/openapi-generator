pipeline {

    agent any

    tools {
        maven 'Maven'
        jdk 'jdk_17'
    }


    stages {
         

        stage("TEST") {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
 

    }

}