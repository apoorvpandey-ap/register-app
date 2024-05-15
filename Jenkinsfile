pipeline {
    agent {'jenkins-agent'}
    tools {
        jdk 'Java17'
        maven   'Maven3'
    }
    stages {
        stage ("clean workspace"){
            steps {
                cleanWS()
            }
        }stage ("checkout from scm"){
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/apoorvpandey-ap/register-app'
            }
        }stage ("build application"){
            steps {
                sh "mvn clean package"
            }
        }stage ("test application"){
            steps {
                mvn test
            }        

        }
    }
}
