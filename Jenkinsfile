pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the code(Tools like Maven and Gradle)..'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests (Tools like TestNG, Selenium)..'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Running code analysis(Tool: SonarQube)..'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan(Tools: OWASP ZAP or Snyk)..'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging (AWS EC2 instance using Terraform)'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging(Postman for API Testing)..'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production... test'
            }
        }
    }
    post {
        always {
            echo 'Pipeline succeeded!'
           
                to: 's223743838@deakin.edu.au',
                subject: "Jenkins Pipeline Success: ${currentBuild.fullDisplayName}",
                body: "The Jenkins pipeline ${currentBuild.fullDisplayName} was successful.",
                attachlog: true
        }
        failure {
            echo 'Pipeline failed!'
            
                to: 's223743838@deakin.edu.au',
                subject: "Jenkins Pipeline Failure: ${currentBuild.fullDisplayName}",
                body: "The Jenkins pipeline ${currentBuild.fullDisplayName} failed. Please review the attached logs.",
                attachLog: true
            
        }
    }
}
