pipeline {
    agent{ label 'Jenkins-Agent'}
    tools {
        jdk 'Java21'
        maven 'Maven3'

    }
    stages{
        stage ("Cleanup Workspace"){
            steps{
                cleanWs()
            }
        }
        stage ("checkout from SCM"){
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/Erhokhon/register-app.git'
            }
        }
        stage ("Build Application"){
            steps{
                sh "mvn clean package"
            }
        }
        stage ("Test Application"){
            steps{
                sh "mvn test"
            }
        }
        
    }
}
