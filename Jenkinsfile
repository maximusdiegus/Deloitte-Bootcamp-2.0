pipeline{
        agent any
        stages{
            stage('Stage 1: Clone repo'){
                steps{
                    sh "git clone  https://gitlab.com/qacdevops/chaperootodo_client"   
                }
            }
            stage('Stage 2: Install Docker & Docker Compose'){
                steps{
                    sh "sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin"
                    sh "DOCKER_CONFIG=${DOCKER_CONFIG:-$HOME/.docker}"
                    sh "mkdir -p $DOCKER_CONFIG/cli-plugins"
                    sh "curl -SL https://github.com/docker/compose/releases/download/v2.14.0/docker-compose-linux-x86_64 -o $DOCKER_CONFIG/cli-plugins/docker-compose"
                }
            }
          stage('Stage 3: Build the job'){
                steps{
                    sh "echo hey"
                }
            }
        }
}
