pipeline {
    agent any
    stages {
        stage {
            steps("Build") {
                sh "mvn clean package"
            }
        }
        stage {
            steps("Deploy") {
                deploy adapters: [tomcat7(credentialsId: 'e17dc212-b71c-481b-9f6c-f881f3dc18c6', path: '', 
                url: 'http://ec2-3-14-132-122.us-east-2.compute.amazonaws.com:8080/')], 
                contextPath: 'javawebproject', war: '**/java-web-project.war'
            }
        }
    }
}
