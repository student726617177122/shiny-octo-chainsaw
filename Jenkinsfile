pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code with Maven...'
                sh 'mvn clean package'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests with JUnit and integration tests with TestNG...'
                sh 'mvn test'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Analyzing code with SonarQube...'
                sh 'sonar-scanner -Dsonar.projectKey=myProject'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Performing security scan with OWASP Dependency-Check...'
                sh 'dependency-check.sh --project myProject --scan .'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying application to staging environment (AWS EC2)...'
                sh './deploy-to-ec2.sh staging'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging with Postman/Newman...'
                sh 'newman run tests.postman_collection.json -e staging_environment.json'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying application to production environment (AWS EC2)...'
                sh './deploy-to-ec2.sh production'
            }
        }
    }
}
