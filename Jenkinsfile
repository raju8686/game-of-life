pipeline{
    tools{
        maven 'Maven_01'
    }
    agent none
    stages{
         stage('checkout'){
              agent any
              steps{
                  git'https://github.com/wakaleo/game-of-life.git'
              }
            }
         stage('compile'){
             agent any
             steps{
                  sh 'mvn compile'
                }
            }
         stage('test'){
             agent any
             steps{
                  sh 'mvn test'
                }
                post{
                    always{
                        junit 'gameoflife-web/target/surefire-reports/*.xml'
                    }
                }
            }
         stage('package'){
             agent any
             steps{
                  sh 'mvn package'
                }
            }
        }
        
    }    
