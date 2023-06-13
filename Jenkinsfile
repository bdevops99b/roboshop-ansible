pipeline {

agent {
node {
label 'workstation'
}
}
parameters {
choice(name: 'env', choices: ['dev', 'prod'], description: 'Pick environment')
string(name: 'component', defaultValue: '', description: 'component name')
}
stages {
 stage('Anisible'){
 steps {
  sh 'ansible-playbook -i ${component}-${env}.panda4u.online, roboshop.yml -e ansible_user=centos -e ansible_password=DevOps321 -e role_name=${component} -e env=${env}'
 }
 }

}
post {
  always {
     cleanWs()
    }
  }

}