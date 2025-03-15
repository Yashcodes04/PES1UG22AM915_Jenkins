pipeline {
    agent any  // Run the pipeline on any available agent

    stages {
        stage('Build') {  
            steps {
                sh 'ls -l'  // List files to verify if program.cpp is present
                sh 'g++ -o output main.cpp'  // Compile the C++ file
                build job: 'PES1UG22AM915-1'  // Trigger the first Jenkins job
            }
        }
        
        stage('Test') {
            steps {
                sh './output'  // Execute the compiled C++ program
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deployment Successful'
            }
        }
    }
    
    post {
        failure {
            echo 'Pipeline failed'  // Print message if any stage fails
        }
    }
}