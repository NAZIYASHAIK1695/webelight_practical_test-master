pipeline {
    agent any
    tools{
        nodejs 'nodejs16.16'
    }

    stages {
        stage('Build') {
            steps {
                sh "npm install"
                sh "npm run build"
            
            }
        }
    }
       stage('Push To ECR') {
            steps {
                sh "docker build -t frontend_app ."
            }
        }
        stage('reomte ec2') {
            steps {
                sh "ansible-playbook playbook.yml"
            }
        }
}
