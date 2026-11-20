pipeline {

     agent { label 'Node1' }

       stages {
          
          stage ( 'clean' )  {

            steps {

               sh 'mvn clean'

                  }

                }

          stage ( 'compile' ) {
 
            steps {

                sh 'mvn compile'

                  }

                 }

          stage ( 'build' )  {

            steps {

                sh 'mvn clean install'

                  }
                }
              }
            }

