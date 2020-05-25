pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                echo 'Building..'
                 git url: "https://github.com/satishchennu1/ansible-oc-jenkinsfile.git", branch: "master"
            }
        }
        stage('Build and Deploy to Dev Environment') {
            steps {
                echo 'Building..'
                ansible-playbook deploy-ieopetclinic-dev.yaml 
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
