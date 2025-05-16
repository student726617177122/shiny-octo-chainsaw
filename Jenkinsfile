pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Simulating build...'
                sh 'echo Building code'
            }
        }

        stage('Unit Test') {
            steps {
                echo 'Running unit tests...'
                sh 'echo All tests passed'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Running static analysis...'
                sh 'echo Code looks clean'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Scanning for vulnerabilities...'
                sh 'echo No critical issues found'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging...'
                sh 'echo Deployed to staging server'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
                sh 'echo Integration test passed'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production...'
                sh 'echo Deployed to production server'
            }
        }
    }
}
