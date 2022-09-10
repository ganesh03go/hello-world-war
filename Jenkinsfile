pipeline {
    agent any

    stages {
        stage('Checkout src') {
            steps {
                echo 'Java-Maven-war-project '
                echo "Branch_Name: ${env.GIT_BRANCH}" 
                git 'https://github.com/rranjith406/hello-world-war.git'
                sh 'ls -lrt'
            }
        }
        stage('Build Stage') {
            steps {
                sh 'mvn clean install'
                echo "build number is: ${env.BUILD_NUMBER}"
                echo "Build url is: ${env.BUILD_URL}"
            }
        }
        stage('Test Stage') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Deploy Stage') {
            steps { 
                echo "this is a deploy stage"
                    }
                }
         
    }
}
