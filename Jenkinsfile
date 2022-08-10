pipeline {
    agent any

    stages {
        stage('scm checkout') {
            steps {
                sh 'whoami'
                git branch: 'main', url: 'https://github.com/brocode77/ansible-ts.git'
            }
        }
         stage('playbook') {
            steps {
                sh 'chmod 777 install.sh useradd.sh'
                sh 'cp userlist.txt /tmp/'
                ansiblePlaybook credentialsId: 'vm1', disableHostKeyChecking: true, installation: 'ansible', playbook: 'project-playbook.yaml'
            }
        }
    }
}
