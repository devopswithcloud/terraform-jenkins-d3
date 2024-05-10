pipeline {
    // if needed create one agent and install terraform on top of it 
    agent any 
    stages {
        // Different Workflows 
        stage('init') {
            steps {
                sh "terraform init"
                sh "ls -la"
            }
        }
        stage ('Validation'){
            steps {
                sh "terraform validate"
            }
        }
        stage ('Plan') {
            steps {
                sh "terraform plan"
            }
        }
        state ('Apply') {
            steps {
                sh "echo terraform apply "
            }
        }
        state ('Destroy'){
            sh "echo terraform destroy "
        }
    }

}