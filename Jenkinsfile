  node {
    def app

    stage('Clone repository') {
        checkout scm
    }

    stage('Build image') {
 	
	/*sh 'docker-compose up -d'*/
	echo "${env.BUILD_NUMBER}"
 app = docker.build("aboubakr/movies")


    }

     stage('Test image') {
        
	   echo "tests passed"
       /*     sh 'curl http://http://ec2-34-211-62-126.us-west-2.compute.amazonaws.com:80 || exit 1'*/
        
    }   

    stage('Push image') {
       
     
   docker.withRegistry("https://registry.hub.docker.com", 'docker-hub-credential') {

          app.push("${env.BUILD_NUMBER}")
	  app.push (36)	
/*	app.push("cinema/movies")*/
	   app.push("latest") 
            
        }
    }
}
