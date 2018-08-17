node() {
   stage('Checkout'){
          checkout scm
       }
   stage('Npm'){
    sh 'npm install' 
    sh 'npm start'
   }
   stage('Deploy'){
    sh "cf login -a ${env.CF_API} -u ${env.CF_USERNAME} -p ${env.CF_PASSWORD} -o ${env.CF_ORG} -s ${env.CF_SPACE}"
              
              sh 'cf apps'
              sh "cf push product-nodejs-app"
              sh 'cf buildpacks'
   }
}     
