pipeline {
    agent any

    environment {
        GIT_REPO_URL = 'https://github.com/Naveenkumarm01/lab5.git'
        NGINX_PATH = 'D:\nginx-1.24.0\nginx-1.24.0\htmldocx'
    }

    stages {
        stage('Checkout') {
            steps {
                script {
                    // Use the checkout step to clone the Git repository
                    checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/Naveenkumarm01/lab5.git']]])
                }
            }
        }

        stage('Deploy to Nginx') {
            steps {
                script {
                    // Using the Jenkins workspace variable to reference files
                    bat 'xcopy /y "C:\\Users\\user\\Desktop\\Namrata_Das_PU\\Fall_AY_2023-24\\Subject_Handled\\DevOps\\pipeline\\index.html" "%NGINX_PATH%"'
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded! You can add additional steps here.'
        }
        failure {
            echo 'Pipeline failed! You may want to take some actions.'
        }
    }
}
  