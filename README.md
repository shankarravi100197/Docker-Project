# Docker-Project

First test code in local

Now create an EC2 instance 

Then SSH it to you local 

Create a directory

Then cd directory

git clone https://github.com/shreys7/django-todo.git

cd django-todo

 sudo apt-get update

 sudo apt-get install python3.6

sudo apt install python3-django

 sudo apt install python3-pip

 pip3 install django

 python3 manage.py migrate

 vi todoApp/settings.py
 (Change TIME_ZONE = 'Asia/kolkata' to TIME_ZONE = 'Asia/Dhaka')

python3 manage.py runserver

 python3 manage.py migrate

Our server is running on 127.0.0.1 (is a Local Host) but we have to expose it to everyone 0.0.0.0

 python3 manage.py runserver0.0.0.0:8000

Then we will go to inbound rules and make Custom TCP of port range 8002 for everyone  

Now we have to add our public ip to    vi todoApp/settings.py   AllowedHost=[PublicIP]

Now go to browser and put PublicIP:8002 and the todo app will be running

lsof -i:8002 (to see what are running on server 8002 )

kill -9 PID   (Put no. in pllace of PID)


Now install Docker  

sudo apt install docker.io


 vi Dockerfile   (make a a docker file)

FROM python:3
RUN pip install django==3.2


COPY . .

RUN python manage.py migrate

CMD ["python","manage.py","runserver","0.0.0.0:8002"]


 sudo docker build . -t todo-app

 sudo docker run -p port no.:port no. docker ID 
sudo docker run -p 8002:8002 ffd4fb45c7ad

 sudo docker run -d -p 8002:8002  ffd4fb45c7ad (to run docker in background)

sudo apt update

sudo apt install openjdk-11-jre

Install Jenkins

curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins


 sudo systemctl enable jenkins   (to unable jenkins)

sudo systemctl start jenkins     (to start jenkins)

 sudo systemctl status jenkins    (to see status of jenkins)

 Give acess to 8080 in Inbound Rules in EC2

 Now put your public IP:8080 in browser and your Jenkins will be running

 
sudo cat /var/lib/jenkins/secrets/initialAdminPassword


 
 

 

 

 




 

 

