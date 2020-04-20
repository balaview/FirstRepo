pipeline {
    agent none
    stages {

        stage('Non-parallel stage') {
         agent {
                   label "master"
                   }
          steps { 
                    echo 'This stage will be executed first'
                    }
          }
                   
        stage('Run Tests') {
            parallel {
                stage('Test On Windows') {
                    agent {
                        label "Windows_Node"
                    }
                    steps {
                         echo "Connected to windows-node which is secondary nore in Parallel Pipeline job"
                       
                    }
                 

                }

                stage('Test On Master') {
                    agent {
                        label "master"
                    }
                    steps {
                        echo "Connected to Master in process of Parallel pipeline Job "
                    }
                    
                }
            }
        }
    }
}
