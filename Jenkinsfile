pipeline{
    agent { label 'Jenkins-Agent'}
    tools {
        jdk 'JAVA17'
        maven 'MAVEN3'
    }
    stages{
        stage("Cleanup Workspace"){
            steps{
                cleanWs()
            }
        }
        stage("Checkout from SCM"){
            steps{
                git branch: 'main', credentialsId:'github', url:'https://github.com/rahul2870/practice_docker-jenkins'
            }
        }
        stage("Build Application"){
            steps {
                sh "mvn clean package"
            }
        }

        stage("Test Application"){
            steps{
                sh "mvn test"
            }
        }
    }
}
