pipeline{
    agent{
        node{
            label 'centos'
        }
    }
    stages{
        stage('Clone GIT repo'){
            git credentialsId: 'c74c6485-9f3a-4da9-bc52-354dc2d5320d', url: 'https://github.com/rajanirugur/sample-java-project-demo1.git'
        }
    }
    stage('Gradle Build'){
        steps{
            sh './gradlew build'
        }
    }
    stage('Docker image Build'){
        steps{
            sh "sudo docker build -t rathinamtrainers/myjavaapp:${env.BUILD_ID} ."
            sh "sudo docker tag rathinamtrainers/myjavaapp:${env.BUILD_ID} rathinamtrainers/myjavaapp:latest"
        }
    }
}
