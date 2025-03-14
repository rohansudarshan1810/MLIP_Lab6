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
                echo 'Test Step: Running pytest using Conda environment'

                source /opt/homebrew/Caskroom/miniconda/base/etc/profile.d/conda.sh
                conda activate mlip

                pytest --maxfail=1 --disable-warnings

                echo 'Tests completed successfully'
                '''
            }
        }
        stage('Deploy') {
            steps {
                sh '''#!/bin/bash
                echo 'In this step, we deploy our project'
                echo 'Depending on the context, we may publish the project artifact or upload pickle files'
                '''
            }
        }
    }
}
