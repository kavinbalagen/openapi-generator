pipeline {

    agent any

    tools {
        maven 'Maven'
        jdk 'jdk_17'
    }
    environment{
        JAVA_HOME = '/Users/kbalasub/.jenkins/tools/hudson.model.JDK/JDK_17/amazon-corretto-17.jdk/Contents/Home'
    PATH = "${env.JAVA_HOME}/bin:${env.PATH}"
    }

    stages {

        stage("TEST") {
            steps {
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