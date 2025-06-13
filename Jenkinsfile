pipeline {
    agent any 
    stages {
        stage('Lint Checks') {
            steps {
                sh "echo 'Running lint checks...'"
                sh "echo 'lint checks completed successfully!'"
            }   
        }
        stage('Sonar Checks') {
            steps {
                sh "echo 'Running Sonar checks...'"
                sh "echo 'Sonar checks completed successfully!'"
            }   
        }
        stage('Parallel Stage : Testing') {
            parallel {
                stage('Unit Testing') {
                    steps {
                        sh "echo 'Running Unit Testing...'"
                        sh "echo 'Unit Testing completed successfully!'"
                        sh "sleep 30"
                    }   
                }
                stage('Integration Testing') {
                    steps {
                        sh "echo 'Running Integration Testing...'"
                        sh "echo 'Unit Integration completed successfully!'"
                        sh "sleep 60"
                    }   
                }
                stage('Functional Testing') {
                    steps {
                        sh "echo 'Running Functional Testing...'"
                        sh "echo 'Unit Functional completed successfully!'"
                        sh "sleep 100"
                    }   
                }
            }    
        }
        stage('Building Artifact') {
            steps {
                sh "echo Running Building Artifact..."
                sh "echo 'Artifact built successfully!'"
            }   
        }
        stage('Tagging The Version') {
            steps {
                sh "echo 'Tagging the version...'"
                sh "echo 'Version tagged successfully!'"
            }   
        }
        stage('Check Versions Availability On Nexus') {
            steps {
                sh "echo 'If its there, dont upload to Nexus...'"
                sh "echo 'If its not there, uploading to Nexus...'"
            }   
        }
    }
}