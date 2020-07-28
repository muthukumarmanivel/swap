pipeline {
 agent any
 parameters {
     choice(name: 'VERSION', choices:['1.1','1.2','1.3','1.4'], description:'TesT')
     booleanParam(name: 'excutetest', defaultValue: true, description:'')
 }
 stages {
  stage('Build') {
   steps {
    echo 'Building'
    git 'https://github.com/muthukumarmanivel/swap.git'
    sh 'ls'
   }
  }
  stage('Test') {
      when {
          expression {
              params.excutetest
          }
      }
   steps {
    echo 'Testing..'
    sh 'uname -a'
   }
  }
  stage('Deploy') {
   steps {
    echo 'Deploying....'
    echo "Deploy with version${params.VERSION}"
   }
  }
 }
}
