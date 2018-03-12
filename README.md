# jenkins2-with-docker
Learning :: How to install/config the Continuous Integration Server with Jenkins on Docker 

* Jenkins master 
* Jenkins data to keep all configuration such as plugins and jobs of Jenkins
```
## build images
docker build -t jenkins-data -f data/Dockerfile .
docker build -t jenkins2 -f master/Dockerfile .

## run images
docker run --name=jenkins-data jenkins-data
docker run -p 8080:8080 -p 50000:50000 --name=jenkins-master --volumes-from=jenkins-data -d jenkins2

## exc password
docker exec jenkins-master cat /var/jenkins_home/secrets/initialAdminPassword
```
