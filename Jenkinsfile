pipeline {
    agent { label 'Jenkins-Agent01' }
    agent { label 'jenkins-Agent02' }
    tools {
        jdk 'Java17'
        maven 'Maven1'
    }
    stages{
        stage("Cleanup Workspace"){
                steps {
                cleanWs()
                }
        {

        stage("Checkout from SCM"){
                steps {
                git branch: 'main', credentilalsId: 'GitHub', url: 'https://github.com/Shivaraj-sagumale/Jenkins'
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
