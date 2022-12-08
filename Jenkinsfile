pipeline{
        agent any
        environment {
                DB_PASSWORD = "1234"
        }
        stages{
            stage('Stage 1: Clone repo'){
                steps{
                        sh "git clone  https://gitlab.com/qacdevops/chaperootodo_client"   
                }
            }
            stage('Stage 2: Install Docker & Docker Compose'){
                steps{
                        sh "sudo apt-get update -S"
                        sh "sudo apt install curl -y | curl jq"
                        sh "curl https://get.docker.com | sudo bash"
                        sh "usermod -aG docker \$(whoami)"
                        sh "mkdir -p $DOCKER_CONFIG/cli-plugins"
                        sh "curl -SL https://github.com/docker/compose/releases/download/v2.14.0/docker-compose-linux-x86_64 -o $DOCKER_CONFIG/cli-plugins/docker-compose"
                        sh "sudo chmod +x /usr/local/bin/docker-compose"
                        
                }
            }
          stage('Stage 3: Build the job'){
                steps{
                        sh "sudo docker-compose pull && sudo -E DB_PASSWORD=${DB_PASSWORD} docker-compose up -d"
                }
            }
        }
}
