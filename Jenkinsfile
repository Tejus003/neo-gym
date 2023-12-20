pipeline {
    agent {label 'project-a'}

    stages {
        // stage('Install Git') {
        //   steps {
        //        sh 'yum install git -y' 
        //    }
        // }
        stage('Git clone') {
            steps {
                git branch: 'main', url: 'https://github.com/Tejus003/neo-gym.git' 
            }
        }
        stage('Dispaly the cloned files') {
            steps {
                 sh 'cd /var/jenkins/workspace/pipeline-neogym'
                 sh 'ls'
            }
        }
        stage('install and enable httpd') {
            steps {
                 sh 'yum install httpd -y'
                 sh 'systemctl start httpd'
            }
        }
        stage('copy the src files to httpd path') {
            steps {
                 sh 'cp -r index.html /var/www/html/'
            }
        }
        
    }
}
