pipeline{
        agent any
        environment {
                DB_PASSWORD = '1234'
        }
        stages{
            stage('Stage 1: Clone repo'){
                steps{
                        sh "rm -rf chaperootodo_client"
                        sh "git clone  https://gitlab.com/qacdevops/chaperootodo_client"   
                }
            }
            stage('Stage 2: Install Docker & Docker Compose'){
                steps{
                        sh "sudo apt-get update"
                        sh "sudo apt install curl -y"
                        sh "curl https://get.docker.com | sudo bash"
                        sh '''sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose'''
                        sh "sudo chmod +x /usr/local/bin/docker-compose"
                }
            }
          stage('Stage 3: Build the job'){
                steps{
                        sh "docker compose version"
                        sh "sudo docker-compose pull && sudo -E DB_PASSWORD=${DB_PASSWORD} docker-compose up -d"
                }
            }
        }
}
