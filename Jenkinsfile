pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''#!/bin/bash
                echo 'In C or Java, we can compile our program in this step'
                echo 'In Python, we can build our package here or skip this step'
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''#!/bin/bash
                echo 'Test Step: We run testing tool like pytest here'

                # Initialize conda if necessary (uncomment if needed)
                source /home/djtan/miniconda3/etc/profile.d/conda.sh || exit 1
                
                # Activate the required conda environment
                source activate myenv || exit 1

                # Run pytest with JUnit XML report
                pytest --junitxml=test-results.xml || exit 1
                
                # exit 1 comment this line after implementing Jenkinsfile
                '''
            }
        }
        stage('Deploy') {
            steps {
                echo 'In this step, we deploy our project'
                echo 'Depending on the context, we may publish the project artifact or upload pickle files'
            }
        }
    }
}
