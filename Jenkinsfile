pipeline {

    agent any

    tools {
        maven 'maven 3.9.0'
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