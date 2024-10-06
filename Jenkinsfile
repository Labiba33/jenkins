pipeline {
    agent any

    stages {
        // Stage 1: Build
        stage('Build') {
            steps {
                echo 'Stage 1: Build - Task: Compile and package the Java project'
                echo 'Tool: Maven for dependency management and building the project'
            }
        }

        // Stage 2: Unit and Integration Tests
        stage('Unit and Integration Tests') {
            steps {
                echo 'Stage 2: Unit and Integration Tests - Task: Run unit tests and integration tests'
                echo 'Tool: JUnit for testing'
            }
            post {
                always {
                    mail to: 'labibatanjimrida@gmail.com',
                         subject: "Unit and Integration Tests: ${currentBuild.fullDisplayName}",
                         body: "Unit and Integration Tests completed with status: ${currentBuild.currentResult}"
                }
            }
        }

        // Stage 3: Code Analysis
        stage('Code Analysis') {
            steps {
                echo 'Stage 3: Code Analysis - Task: Analyze the code for quality and standards'
                echo 'Tool: SonarQube for code analysis'
            }
        }

        // Stage 4: Security Scan
        stage('Security Scan') {
            steps {
                echo 'Stage 4: Security Scan - Task: Perform a security scan on the code'
                echo 'Tool: OWASP Dependency-Check for security scanning'
            }
            post {
                always {
                    mail to: 'labibatanjimrida@gmail.com',
                         subject: "Security Scan: ${currentBuild.fullDisplayName}",
                         body: "Security Scan completed with status: ${currentBuild.currentResult}"
                }
            }
        }

        // Stage 5: Deploy to Staging
        stage('Deploy to Staging') {
            steps {
                echo 'Stage 5: Deploy to Staging - Task: Deploy the application to a staging environment'
                echo 'Tool: Jenkins SSH or Ansible for deployment automation'
            }
        }

        // Stage 6: Integration Tests on Staging
        stage('Integration Tests on Staging') {
            steps {
                echo 'Stage 6: Integration Tests on Staging - Task: Run integration tests in the staging environment'
                echo 'Tool: JUnit for integration tests'
            }
        }

        // Stage 7: Deploy to Production
        stage('Deploy to Production') {
            steps {
                echo 'Stage 7: Deploy to Production - Task: Deploy the application to a production environment'
                echo 'Tool: Jenkins SSH or Ansible for production deployment'
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed.'
        }
    }
}
