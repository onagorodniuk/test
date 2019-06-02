node {
   def test
   stage('get_playbook_from_git') { 
      // Get some code from a GitHub repository
      git 'https://github.com/onagorodniuk/test.git'
   }
   stage('check_conectivity_syntax') {
      
        sh 'ansible web -i inventories/test/hosts --key-file ~jenkins/.ssh/key.pem -m ping'
        sh 'ansible-playbook --syntax-check test.yml -i inventories/test/hosts --key-file ~/.ssh/key.pem' 
    }
    
   stage('run_playbook') {
       sh 'ansible-playbook test.yml -i inventories/test/hosts --key-file ~/.ssh/key.pem' 
      
   }
}