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
                env.JAVA_HOME = tool name: 'jdk_17', type: 'jdk'
                
                }
                sh 'printenv'
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