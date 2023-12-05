pipeline {
            agent any
            stages {
 //                   stage ("checkout") {
  //                      steps {
 //                           git branch : "main", url : "https://github.com/Hernan-Berrios/Petclinic"
//                        }                
//                    }
                stage ("build") {
                        steps {
                            sh "./mvnw package"
                        }
                }
                stage ("capture") {
                        steps {
                            archiveArtifacts  '**/target/*.jar'
                            jacoco()
                            junit '**/target/surefire-reports/TEST*.xml'
                        }
                }
            }
        post {
            success {
            // One or more steps need to be included within each condition's block.
            sh "echo OK"
            }
        }
        }
