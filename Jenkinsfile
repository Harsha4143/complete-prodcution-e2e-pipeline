pipeline{
    agent{
        label "java"
    }
    tools {
        jdk 'Java17'
        maven 'Maven3'
    }
    environment {
        APP_NAME = "complete-prodcution-e2e-pipeline"
        

    }
    stages{
        stage("Cleanup Workspace"){
            steps {
                cleanWs()
            }

        }
    
        stage("Checkout from SCM"){
            steps {
               checkout scm
            }

        }

        stage("Build Application"){
            steps {
                sh "mvn clean package"
            }
            steps {
                sh "mvn clean install"
            }

        }

        stage("Test Application"){
            steps {
                sh "mvn test"
            }

        }
}
}
