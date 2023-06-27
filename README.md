# Lab6
Requirements:
Windows 11
Have a docker desktop installed

Pull the lab 6 document and unzip it on your desktop. 
Note: If you have a Windows PC with onedrive make sure that you do not have the folder on onedrive.

In the  Flaskapp folder locate the app.py file and change the radius_secret to one of your choosing. 
 RADIUS_SECRET = b'cream_cheese'

Make sure the ip address ends in 2
RADIUS_SERVER = '172.17.0.2'


In the free radius folder locate the Clients.conf file and change the secret to one of your choosing.
  secret = cream_cheese 

Locate the authorize file and change the password to one of your choosing.
maya    Cleartext-Password := "cheesesticks" 
 

Open powershell or the Command prompt in administrative mode. 

cd to the directory where you have the lab_6 folder
ls to inspect the contents and notice the freeradius file and flaskapp file


Build the free radius image and container
cd into the freeradius file

Run the following command to build the docker image
# docker build . -t freeradius_image

Run the following command to create the docker container
# docker run -d --name freeradius_container -p 1812:1812/udp -p 1813:1813/udp freeradius_image

Build the flash app image and container
Run the following command to build the docker image
# docker build . -t flask_image

Run the following command to build the docker container
# docker run -d --name flask_container -p 5000:5000/tcp flask_image

Make sure to create the free radius container first or there will be authentication issues.
 

Open a bower and authenticate using the following website
http://172.0.0.1:5000

Login with your username and password
It may take a few minutes to load, if it fails 
make sure you do not have any other instances of the browser running.
Check the ip address in the flaskapp in the file app.py it should end in 2 not 3
Restart your containers and have the freeradius start then the flaskapp

