pipeline {

    agent any

    tools {
        maven 'Maven'
        jdk 'jdk_17'
    }


    stages {

        stage("TEST") {
            steps {
                script{
                env.JAVA_HOME="${tool 'jdk_17'}"
                env.PATH="${env.JAVA_HOME}/bin:${env.PATH}"
                }
                sh 'mvn clean package -Dmaven.test.skip=true -Dmaven.javadoc.skip=true -pl modules/openapi-generator-cli -am'
            }
        }
    }
    post{
        success{
            archiveArtifacts artifacts:'modules/openapi-generator-cli/target/openapi-generator-cli.jar' , fingerprint: true
        }
    }
}