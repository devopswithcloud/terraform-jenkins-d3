pipeline {
    // if needed create one agent and install terraform on top of it 
    agent any 
    parameters {
        choice (
            name: 'action',
            choices: 'apply\ndestroy',
            description: "Apply and destory the infra"
        )
    }
    stages {
        // Different Workflows 
        stage('init') {
            when {
                expression {
                    params.action == 'apply'
                }
            }
            steps {
                sh "terraform init"
                sh "ls -la"
            }
        }
        stage ('Validation'){
            when {
                expression {
                    params.action == 'apply'
                }
            }
            steps {
                sh "whoami"
                sh "pwd"
                sh "terraform validate"
            }
        }
        stage ('Plan') {
            when {
                expression {
                    params.action == 'apply'
                }
            }
            steps {
                sh "terraform plan"
            }
        }
        stage ('Apply') {
            // Eventually u should be having an approval here 
            // input statemetn
            when {
                expression {
                    params.action == 'apply'
                }
            }
            steps {
                sh "echo terraform apply "
            }
        }
        stage ('Destroy'){
            when {
                expression {
                    params.action == 'destroy'
                }
            }
            steps {
                sh "echo terraform destroy "
            }
        }
    }

}