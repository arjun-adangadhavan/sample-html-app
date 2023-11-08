node("slave"){
    stage("clone"){
        git branch: 'main', url: 'https://github.com/arjun-adangadhavan/sample-html-app.git'
        sh "ls"
    }
    stage("image"){
        sh "docker build -t dante97/html-app ."
    }
    stage("docker-hub"){
        sh "docker login -u dante97 -p Arjun1997//"
        sh "docker push dante97/html-app"
    }
    stage("container"){
        sh "docker rm -f html-app"
        sh "docker run -d -p 80:80 --name=html-app dante97/html-app"
    }
}
