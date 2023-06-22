# docker-pipeline

```
FROM jenkins/jenkins:lts

USER root

RUN apt-get update -qq \
    && apt-get install -qqy apt-transport-https ca-certificates curl gnupg2 software-properties-common

RUN curl -fsSL https://download.docker.com/linux/debian/gpg | gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

RUN echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/debian $(lsb_release -cs) stable" | tee /etc/apt/sources.list.d/docker.list > /dev/null

#RUN apt-get update -qq \
#    && apt-get -y install docker-ce docker-ce-cli containerd.io

RUN curl -fsSL https://get.docker.com -o get-docker.sh \
    && sh get-docker.sh

RUN usermod -aG docker jenkins

USER jenkins
```



<h3> image Build command </h3>
 ```docker build -t jenkins-container-2 .```

<h3> Command to run </h3>

```docker run -p 8080:8080 -p 50000:50000 -v /var/run/docker.sock:/var/run/docker.sock -v /Users/xs296-piydhi/Desktop/helm/jenkins:/var/jenkins_home jenkins-container-2```

<h3>go inside jenkins container as a ```Root``` </h3>

```docker exec -it --user root de84d6dfb33b  /bin/bash```
<h3>Inside the container </h3>
```chmod 777 var/run/docker.sock```
