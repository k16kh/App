pipeline
{
         agent any
           stages {
               stage('Pull') {
                    steps{
                       script{
                           checkout([$class: 'GitSCM', branches: [[name: '*/master']],
                               userRemoteConfigs: [[
                                   url: 'https://github.com/k16kh/app.git']]])
                    }
                }
            }
               stage('Build')
               {
                              steps {
                                     script{
                                     sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml "
                                           }
                                    }
                            }
                 
        }
}
