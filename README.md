# Usage
  - Get the docker image first. To get the image, please prepare a computer with docker installed and network environment is fine. Then run the following command in terminal:
```sh
$ docker pull taizai/webpagetest
```
  - After pulling the docker image, please run the following commnad to start the Jenkins service:
```sh
$ docker run -p 8080:8080 -t -i -u root taizai/webpagetest /bin/bash -c "JENKINS_HOME=/var/lib/jenkins /usr/bin/java -jar /usr/share/jenkins/jenkins.war"
```
  - After executing command, the terminal will output some messages. Now you can open the browser to access Jenkins. If you run docker on remote server, please open http://REMOTE_SERVER_IP:8080 to access Jenkins service.(Please replace the REMOTE_SERVER_IP by the server's IP address). If you run docker on your local machine, please open http://localhost:8080 or http://127.0.0.1:8080 to access Jenkins service.
  - When you open the Jenkins page, you will see a finished task. You can read the report by clicking the task or trigger the testing task again. However, all the report html file could not be read on the Jenkins directly, you need to download all the report files because there is an unsolved bug(https://issues.jenkins-ci.org/browse/JENKINS-32118) had been reported.
  - To trigger the testing task again, the docker need to run with network environment because the testing script is put at github and Jenkins will download the script every time you trigger the tasting task.
