pipeline {
    agent { label 'Jenkins-Agent01' }
    tools {
        jdk 'java17'
        maven 'Maven1'
    }
    stages{
        stage("Cleanup Workspace"){
                steps {
                cleanWs()
                }
        }
        stage("Checkout from SCM"){
                steps {
                git branch: 'main', credentialsId: 'GitHub', url: 'https://github.com/Shivaraj-sagumale/Jenkins'
                }
        }
        stage("Build Application"){
            steps {
                sh "mvn clean package"
            }
        }

        stage("Test Application"){
            steps {
                  sh "mvn test"
            }
        }
        
    }
}
