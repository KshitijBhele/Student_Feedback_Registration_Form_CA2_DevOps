pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo '========================================='
                echo 'Step 1: Checking out project files'
                echo '========================================='
                echo 'Project files loaded successfully.'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo '========================================='
                echo 'Step 2: Installing Python and Selenium dependencies'
                echo '========================================='
                bat 'pip install --upgrade pip'
                bat 'pip install selenium'
                bat 'pip install webdriver-manager'
            }
        }

        stage('Run Selenium Tests') {
            steps {
                echo '========================================='
                echo 'Step 3: Running Selenium test cases'
                echo '========================================='
                bat 'python -m unittest test_feedback_form.py -v'
            }
        }

        stage('Results') {
            steps {
                echo '========================================='
                echo 'Step 4: Test execution completed'
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
            echo '❌ BUILD FAILED: Check logs above'
        }
    }
}
