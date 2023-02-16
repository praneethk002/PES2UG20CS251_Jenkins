pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building code...'
                sh 'make -C main'
                sh 'chmod +x compile_script.sh'
                sh './compile_script.sh'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing code...'
                sh 'chmod +x test_script.sh'
                sh './test_error_script.sh'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying code...'
            }
        }
    }

    post {
        always {
            echo 'Finished pipeline...'
        }
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed...'
        }
    }
}
