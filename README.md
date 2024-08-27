# node-todo-cicd

CREATE AN EC2 INSTACE AND GIVE IT TO PERMISSION FOR "ALL TRAFFIC".
RUN THESE ALL COMMMAND
do ssh for machine access--------------------------------------------------------------------
     sudo apt update
     sudo apt install openjdk-11-jre
    java -version
    curl -fsSL https://pkg.jenkins.io/debian/jenkins.io.key | sudo tee \   /usr/share/keyrings/jenkins-keyring.asc > /dev/null 
    echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \   https://pkg.jenkins.io/debian binary/ | sudo tee \   /etc/apt/sources.list.d/jenkins.list > 
    /dev/null
    sudo apt-get update 
    sudo apt-get install jenkins
    sudo systemctl enable jenkins
    sudo systemctl start jenkins
    sudo systemctl status jenkins

Adjust Firewall
Ensure that your firewall allows traffic on the Jenkins port (8080):-------------------------------------
go to your ec2 machine security and click on security group 
now add inbound rules 
and custom tcp ip on 8080 ip
and access jenkins thourgh you public ip and :8080
now set your jenkins
for passwprd 
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
sudo apt install docker.io
docker --version

now create docker file 
vi Dockerfile 
sudo apt install docker.io
FROM node:12.2.0-alpine
WORKDIR app
COPY . .
RUN npm install
EXPOSE 8000
CMD ["node","app.js"]
:wq

docker build . -t node-app
sudo usermod -a -G docker $USER
docker run -d --name node-todo-app -p 8000:8000 todo-node-app
Got to jenkins job
Execute shell 

docker build . -t node-app-todo
docker rm -f node-app-todo
docker run -d --name node-app-container -p 8000:8000 node-app-todo
your project hosted


Run these commands:
`sudo apt install nodejs`
`sudo apt install npm`
`npm install`
`node app.js`

