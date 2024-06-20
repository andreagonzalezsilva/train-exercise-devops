pipeline{
    agent { label 'aws-agent' }
    environment{
        TOKENAWS = credentials('controller-ssh-key')
    }
    stages{ 
        stage('Deploy to Testing'){
            steps{
            sh 'ssh -T -oStrictHostKeyChecking=no -i "$TOKENAWS" ec2-user@52.90.131.3 " sudo dnf update; sudo dnf install git -y; sudo dnf install -y httpd; sudo systemctl start httpd; sudo rm -Rf /var/www/html/; sudo git clone https://github.com/andreagonzalezsilva/train-exercise-devops /var/www/html"'
            }
        }
        stage('Deploy to Staging'){
            steps{
            sh 'ssh -T -oStrictHostKeyChecking=no -i "$TOKENAWS" ec2-user@54.224.231.17 " sudo dnf update; sudo dnf install git -y; sudo dnf install -y httpd; sudo systemctl start httpd; sudo rm -Rf /var/www/html/; sudo git clone https://github.com/andreagonzalezsilva/train-exercise-devops /var/www/html"'
            }
        }
        stage('Deploy to Production_Env1'){
            steps{
            sh 'ssh -T -oStrictHostKeyChecking=no -i "$TOKENAWS" ec2-user@3.84.126.99 " sudo dnf update; sudo dnf install git -y; sudo dnf install -y httpd; sudo systemctl start httpd; sudo rm -Rf /var/www/html/; sudo git clone https://github.com/andreagonzalezsilva/train-exercise-devops /var/www/html"'
            }
        }
        stage('Deploy to Production_Env2'){
            steps{
            sh 'ssh -T -oStrictHostKeyChecking=no -i "$TOKENAWS" ec2-user@18.232.141.106 " sudo dnf update; sudo dnf install git -y; sudo dnf install -y httpd; sudo systemctl start httpd; sudo rm -Rf /var/www/html/; sudo git clone https://github.com/andreagonzalezsilva/train-exercise-devops /var/www/html"'
            }
        }
    }
}