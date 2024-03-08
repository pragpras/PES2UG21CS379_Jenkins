pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Compile the .cpp file using a shell script
                    def cppFileName = 'newfile.cpp'
                    sh "g++ -o ${cppFileName.replaceAll('.cpp', '')} ${cppFileName}"
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Print the output of the compiled .cpp file using a shell script
                    def executableName = 'newfile'
                    sh "./${executableName}"
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
