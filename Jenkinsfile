pipeline {
    agent any

    stages {
        stage('Checkout src') {
            steps {
                echo 'Java-Maven-war-project '
                echo "git committer name: ${env.GIT_COMMITTER_NAME}" 
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
         stage("SonarQube analysis") {
            agent any
            steps {
              withSonarQubeEnv('SonarQube-8.9.1') {
                sh 'mvn clean package sonar:sonar'
              }
            }
        }
    }
}
