pipeline {
    agent any

    environment {
        PYTHON_VERSION = '3.13'
        WORKSPACE_DIR = '${WORKSPACE}'
    }

    stages {
        stage('Checkout') {
            steps {
                echo '========================================='
                echo 'Step 1: Checking out project files'
                echo '========================================='
                // In Jenkins, files are automatically checked out
                echo 'Project files loaded successfully.'
                bat 'dir'
            }
        }

        stage('Environment Setup') {
            steps {
                echo '========================================='
                echo 'Step 2: Setting up Python environment'
                echo '========================================='
                bat 'python --version'
                bat 'pip --version'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo '========================================='
                echo 'Step 3: Installing Python and Selenium dependencies'
                echo '========================================='
                bat 'pip install selenium webdriver-manager'
            }
        }

        stage('Run Selenium Tests') {
            steps {
                echo '========================================='
                echo 'Step 4: Running Selenium test cases'
                echo '========================================='
                bat 'python -m unittest test_feedback_form.py -v'
            }
        }

        stage('Generate Test Report') {
            steps {
                echo '========================================='
                echo 'Step 5: Test execution completed'
                echo '========================================='
                echo 'All tests finished successfully!'
            }
        }
    }

    post {
        always {
            echo '========================================='
            echo 'Pipeline Execution Completed'
            echo '========================================='
        }
        success {
            echo '✅ BUILD SUCCESSFUL: All Selenium test cases PASSED!'
        }
        failure {
            echo '❌ BUILD FAILED: One or more test cases FAILED. Check logs above.'
        }
    }
}
