pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                echo 'Building..'
                 git url: "https://github.com/virtapp/k3s-ansible-install-ha.git", branch: "master"
            }
        }
        stage('Build and Deploy to Dev Environment') {
            steps {
                echo 'Building..'
                //sh 'sudo ansible-playbook deploy-ieopetclinic-dev.yaml'
                //ansiblePlaybook installation: 'ansible', playbook: '/root/ansible-oc-jenkinsfile/deploy-ieopetclinic-dev.yaml'
                  sh ' echo "starting Ansible Build and deploy"'
                  sh ' ansible-playbook site.yml -i inventory/sample/hosts.ini"'
              
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
