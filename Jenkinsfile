pipeline {
 agent {label 'ANSIBLE'}
  stages {
     stage ("vcs") {
        steps {
          git url: "https://github.com/thatikrishna/wildfly.git",
          branch: "main"
        }
    }
     stage ("ansible") {
        steps ("playbook") {
          sh "ansible -i hosts -m ping node"
          sh "ansible-playbook -i hosts wildfly.yaml"
        }
    }
  }
}