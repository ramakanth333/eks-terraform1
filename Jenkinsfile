pipeline{
    agent any;

    stages{
        stage('git checkout'){
            steps{
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'eks', url: 'git@github.com:ramakanth333/eks-terraform1.git']])
            }
        }
        stage('terraform init'){
            steps{
                sh 'terraform init'
            }
        }
        stage('terraform validate'){
            steps{
                sh 'terraform validate'
            }
        }
        stage('terraform -auto-approve'){
            steps{
                sh 'terraform -auto-approve'
            }
        }
    }
}
