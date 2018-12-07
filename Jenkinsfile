node('docker') {
 
    stage 'Checkout'
        checkout scm
    stage 'Build & UnitTest'
        sh "npm install"	
        sh "npm run build"
    
    stage 'Pusblish UT Reports'
        sh "docker build -t anthonyalex/seedapp:${env.BUILD_ID} -f Dockerfile ."	 
        sh "docker login -u ${env.} -p ${env.JOB_NAME}"	
        sh "docker push anthonyalex/seedapp:${env.BUILD_ID}"
		sh "docker logout
      
}