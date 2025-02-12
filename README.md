#-------------------------------------------------


Install Docker on Ubuntu 18.04
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
```
sudo apt update
sudo apt install apt-transport-https
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | gpg --dearmor -o /etc/apt/trusted.gpg.d/docker.gpg
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
sudo apt update
sudo apt install docker-ce
sudo systemctl status docker
sudo usermod -aG docker $USER
>>>logout/login<<<
```


Install Jenkins on Ubuntu 18.04
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
```
sudo apt update
sudo apt install openjdk-17-jdk
wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
echo deb http://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list
sudo apt update
sudo apt install jenkins
sudo systemctl start jenkins
sudo systemctl status jenkins

#Получение пароля для первичного входа
sudo cat /var/lib/jenkins/secrets/initialAdminPassword


