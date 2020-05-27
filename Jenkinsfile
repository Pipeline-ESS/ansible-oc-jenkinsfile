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
                //sh 'sudo ansible-playbook deploy-ieopetclinic-dev.yaml'
                //ansiblePlaybook installation: 'ansible', playbook: '/root/ansible-oc-jenkinsfile/deploy-ieopetclinic-dev.yaml'
                  sh ' echo "starting Ansible Build and deploy"'
                  sh '''
                       ssh -t ec2-user@10.201.36.28 'cd /home/ec2-user/ansible-oc-jenkinsfile && ansible-playbook deploy-ieopetclinic-dev.yaml'
                  '''
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
