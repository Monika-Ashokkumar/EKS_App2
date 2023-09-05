node{
    def buildNumber = BUILD_NUMBER
    
    stage("git clone"){
        git url: 'https://github.com/Monika-Ashokkumar/EKS_App2.git', branch: 'main'
        }
        
    
    stage("Build docker image"){
        sh "docker build -t monikaashokkumar/eks_app2 ."
    }
     
    stage("login and push") {
        withCredentials([string(credentialsId: 'dockerPass', variable: 'dockerPass')]) {
    	sh "docker login -u monikaashokkumar -p ${dockerPass}"
    	sh "docker push monikaashokkumar/eks_app2:latest"
        }
    }
}
