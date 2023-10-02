# LEMP-STACK-PROJECT

## Lemp-stack  implementation project.

## Connecting Git bash to AWS is the first step .

![shh -i](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/cf63723d-6fa1-4e1a-a210-fe725da36aa0)

## Step 1- Installation the Nginx Web Server.

We start  by updating server apt package index aso that you can use it command 'sudo apt install nginx' to install Ngix as a web server .

These is shown on the two screenshots attached below.

![sudo apt update](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/66240fe2-e63a-44c3-8c51-1fdfa24274e0)

![sudo apt install nginx](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/2e5d27b1-0f33-4423-95d6-9684a79ca2aa)

 To ensure Nginx web server is installed and is running in the cloud ,we use the command  '$ sudo systemctl status nginx'
 
this is always highlighted in green writing as active(running) as demonstrated below.
 
![sudo systemctl Nginx](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/3064318d-19ff-4567-b988-fa375d0125c3)

To be able toto get any traffic to the Nginx webserver, we need to open a default port 'TCP port 80' that will allow web browsers to web pages in the 

internet from any IP address hence showing the source to be  '0.0.0.0/0' as demonstrated below

![tcp port 80](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/0b362f08-7a9d-49bc-b06e-b768133b4849)

fist we try and chech if we can access the webserver in the ubuntu shell usind the curl commands:

- $ curl http://localhost:80

or

- $ curl http://127.0.0.1:80

In this project the first command was used .

![curl command](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/91907b2e-928d-416c-baea-42aad5caadcf)

 To acess the web server on the browser, we need to use our IP address from AWS. You can go and get the ip adress fron the console on the instance or
 
you can retrive it using the following command curl -s http://169.254.169.254/latest/meta-data/public-ipv4 Aas demonstated by the screen shots below.

![ip address retrival](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/920fcfda-4990-4306-87be-2248b0882514)

![console ip address](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/80419a44-e4c0-46bf-9d5b-a1243f32f621)

 URL http://<Public-IP-Address>:80 helps use to test the Nginx server can respond to requests from the internet.  below page is what is expected to 
 
 demonstrate these.

 ![nginx from the web](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/b40acfc0-7ccf-4952-9d4e-3a3ca997cafd)


 ## Step- 2 Installing MySQL
 
$ sudo apt install mysql-server  is a the first commands used to help install MySQL to enable us handle database on Nginx Sserver.

See below screenshot.

![install mysql server](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/0f992100-f407-4f05-b568-cb8eebe71372)

To connect to the Mysql to administrative data base root, we run a command '$ sudo mysql' the screenshot below demonstrates the output expected to 

show the conection has taken place.

![sudo mysql](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/692a50f8-8b2c-45d1-b3e1-ac957fdae830)

To remove any insecure default settings and lockdown to any user , we set a password to the root user .  This is run using the commands demonstrated

by the screen shots below. 

![remove insecure default settings](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/f9ecd949-d6e4-4e61-8c1d-6d59d31c9bb0)

 From here noew we camn have the mandate to to start the interactive script by making a choice to set up a password or no proceed without one.

 By running the commands $ sudo mysql_secure_installation which will give you several step to step triggers. In this project No password was set up.
 
 ![mysql secure installation](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/f5a82139-3f46-4191-9fee-0411892a5231)

 Incase one used a password, You can run the command $ 'sudo mysql -p' with -p as a trigger for password  then at exit MySQL.

 You need to user use a password to commect to the root user .For security purposes it is important to have user accounts with less expansive 
 
 priviledges set up for every database.

 Running the commandd below shows your data base is working.

 ![image](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/106a08b7-3416-4809-b205-891a5cbb63bb)


 


 


 

 

 
















 


 

 



















 





