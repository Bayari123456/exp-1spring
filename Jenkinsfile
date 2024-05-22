pipeline {
    agent any 
    tools { 
        maven 'maven'
    }
    
    stages {
        stage ("Clean up"){
            steps {
                deleteDir()
            }
        }
        stage ("Clone repo"){
            steps {
                sh "git clone https://github.com/Bayari123456/exp-1spring.git"
            }
        }
       stage ("Generate backend image"){
            steps { 
                dir("exp1-spring"){
                    sh"mvn clean install"
                    sh"docker build -t dockexp1-spring  ."
                }
            }
       }
            stage ("run docker compose"){
            steps { 
                dir("exp1-spring"){
                    sh"docker compose up -d"
                }
            }
            }   
    }
}
        
