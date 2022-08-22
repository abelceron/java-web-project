pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                sh "mvn clean package"
            }
        }
        stage('Deploy'){
            steps{
                deploy adapters: [tomcat7(credentialsId: '9f6ed796-4de9-4f8d-a164-4f905b3f0d06',
                path: '',
                url: 'http://ec2-3-83-182-217.compute-1.amazonaws.com:8080')],
                contextPath: 'javawebapp',
                war: '**/java-web-project.war'
            }
        }
    }
}