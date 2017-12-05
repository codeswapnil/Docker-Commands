-----------docker installation-------------
sudo apt-get update
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo apt-key fingerprint 0EBFCD88
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
sudo apt-get update
sudo apt-get install docker-ce



---------------linux installation---------------
sudo systemctl status docker
docker run hello-world
docker pull ubuntu
docker run ubuntu
docker images
docker run -it ubuntu
docker stop $(docker ps -a -q)//for stopping all containers
docker rm $(docker ps -a -q)//for remove all containers
------------------project management[odoo]----------
docker run -d -e POSTGRES_USER=odoo -e POSTGRES_PASSWORD=odoo --name db postgres:9.4

docker run -p 8069:8069 --name odoo --link db:db -t odoo

on system browser :-localhost:8069
---------------------bug tracking[redmine]----------------

wget https://raw.githubusercontent.com/sameersbn/docker-redmine/master/docker-compose.yml

docker run --name=postgresql-redmine -d \
  --env='DB_NAME=redmine_production' \
  --env='DB_USER=redmine' --env='DB_PASS=password' \
  --volume=/srv/docker/redmine/postgresql:/var/lib/postgresql \
  sameersbn/postgresql:9.6-2

docker run --name=redmine -d \
  --link=postgresql-redmine:postgresql --publish=10083:80 \
  --env='REDMINE_PORT=10083' \
  --volume=/srv/docker/redmine/redmine:/home/redmine/data \
  sameersbn/redmine:3.4.2

-----------------------------pushing on docker hub--------
docker commit [image id]
docker exit
docker login
docker tag hello-world akashmore/helloworldchamp
docker push akashmore/helloworldchamp

---------------------------wordpress-----------------
for mysql:
docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=619619champ -d mysql

for wordpress: 
docker run --name some-wordpress --link some-mysql:mysql -p 8080:80 -d wordpress
------------------------------Debian package-----------------
mkdir sample
cd sample
mkdir DEBIAN
cd DEBIAN
nano control
[
Package: sample
Version: 1.0.0
Section: base
Priority: optional
Architecture: all
Depends: debconf (>= 0.2.26)
Maintainer: akash
Description: Hello World!
]
cd ..
mkdir usr
cd usr
mkdir bin
cd bin
gedit hello.c
gcc hello.c -o hello
cd
sudo apt-get install build-essential
sudo dpkg-deb --build sample/
sudo dpkg -i sample.deb
hello

------------------------------git------------------------
sudo apt-get install git
crate folder
add your files in folder
create a repository in github
on your created folder:
   git init
   git add .
   git commit -m "first"
   git remote add origin https://github.com/akashmore/demo.git
   git push -u origin master
--------------------------------------JIRA-------------------------------

sudo docker pull cptactionhank/atlassian-jira
sudo docker run --detach --publish 8083:8080 cptactionhank/atlassian-jira


-------------------------------------ftp--------------------------------

sudo docker pull stilliard/pure-ftpd
docker run -d --name ftpd_server -p 21:21 -p 30000-30009:30000-30009 -e "PUBLICHOST=localhost" stilliard/pure-ftpd
docker exec -it ftpd_server /bin/bash
pure-pw useradd bob -f /etc/pure-ftpd/passwd/pureftpd.passwd -m -u ftpuser -d /home/ftpusers/bob


normal:
 sudo apt-get install vsftpd
 configure file gedit /etc/vsftpd.conf
 systemctl restart vsftpd
 ftp localhost/ip   
--------------------------------------linux kernel compile code-------------------------
goto website kernel.org and download kernel 
extract kernel 
goto linux folder
type sudo apt-get install build-essential gcc libncurses5-dev libssl-dev
type command :make menuconfig
save and exit
make
make modules_install
make install
mkinitframes -o /boot/initrd.img-3.2.96 3.2.96
update grub
reboot
check with uname -r command



