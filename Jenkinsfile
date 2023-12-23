pipeline {
    environment {
        AWS_ACCESS_KEY_ID     = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
    }

   agent  any
    stages {
        stage('Fetch Terraform Files') {
            steps {
                // Clone the Terraform files from Git
                git branch: 'main', url: 'https://github.com/Mohammedaslaan/complete-terraform-ansible-integration-dnf.git'
            }
        }
        stage('Plan') {
            steps {
                sh 'terraform init'
                sh "terraform plan"
            }
        }
        
        stage('Apply') {
            steps {
                sh " terraform apply -auto-approve"
            }
        }
    }

  }
