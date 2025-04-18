pipeline {
    agent any  // Use any available agent

    tools {
        maven 'Maven'  // Ensure this matches the name configured in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out the code from GitHub'
                git branch: 'main', url: 'https://github.com/Aditi-Sinha-2003/MyMavenApp1.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application'
                sh 'mvn clean package'  // Run Maven build
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests'
                sh 'mvn test'  // Run unit tests
            }
        }

        stage('Run Application') {
            steps {
                echo 'Running the JAR application'
                sh 'java -jar target/MyMavenApp-1.0-SNAPSHOT.jar'
            }
        }
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}


        
