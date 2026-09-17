pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/bbhavanasree2212-code/online-exam-parallel.git'
            }
        }

        stage('Parallel Checks') {

            parallel {

                stage('Frontend Check') {
                    steps {
                        bat 'python frontend_check.py'
                    }
                }

                stage('Backend Check') {
                    steps {
                        bat 'python backend_check.py'
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Online Examination System checks completed.'
                echo 'Deployment successful.'
            }
        }
    }
}
