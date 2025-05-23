
 node{
  
  stage('Clone'){
  
  git branch: 'main', url: 'https://github.com/srinfotech7358/onlinebookstore.git'
  }

  stage ('Build'){
  
  bat 'mvn clean install'
  }

  stage ('Test'){
  
  bat 'mvn test'
  }

  stage('Generate Artifacts') {
  
  archiveArtifacts artifacts: 'target/*.war', followSymlinks: false
  
  }


  
  }
