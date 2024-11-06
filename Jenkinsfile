pipeline {

    agent any

    tools {
        Maven 'Maven 3.9.0'
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