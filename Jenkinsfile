pipeline {
    agent any

    stage('one') {
            steps {
                echo 'Hello, this is srujana'
            }
        }
    stage('Two') {
            steps {
                input('Do you want to proceed?')
        }
    }
    stage('Three') {
            when {
                not {
                       branch "master"
                }
            }
            steps {
                echo "Hello"
            }
          
    }
    stage('Four') {
                    parallel {
                          stage('Unit Test') {
                                             steps {
                                                   echo "Running the unit test.."                                             }
                                             }
                            }
                            stage('Integration Test') {
                                               agent {
                                                     docker {
                                                             reuseNode false
                                                             image 'ubuntu'
                                                     }
                                               }
                                               steps {
                                                     echo "Running the integration test.."
                                               }
                            }
                    }
                }
