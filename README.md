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

 ## Step -3 Installing PHP

 $ sudo apt install php-fpm php-mysql as a command is used to install

 - php-fpm (PHP fastCGI process manager ) and tell Nginx to pass PHP requests to these software for processing

 -  php MySQL allows PHP to communicate with Mysql based database

   A trigger of y/n is expected to allow installation .

See the screenshot below of the sreen results.


 ![php-fpm php-mysql](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/a7b7dfc5-8d68-4e78-9158-e007eaf40f6f)


## Step-4 Configuring nginx to use PHP processor.

We create a directory to allow use to host multiple sites(SERVER BLOCKS) as Nginx on Ubuntu has a default directory  /var/www/html which we leave in 

place incase the client request doesn't match any other site . We then assisgn ownership of the set up directory  .

 we later need to create a file directory. Later we now activate the file  by linking it to the which will pass the make Nginx to use the conf file next time its reloaded.
 
 Lastly you can now test the configuration
 
  All the above are set up usinfg the following commands as listed below and results showwn on the screenshot there after which shows the commands as
  
  the last three commands run on the screenshot.

  - $ sudo mkdir /var/www/projectLEMP

-  $ sudo chown -R $USER:$USER /var/www/projectLEMP

- $ sudo nano /etc/nginx/sites-available/projectLEMP

- $ sudo ln -s /etc/nginx/sites-available/projectLEMP /etc/nginx/sites-enabled/

- $ sudo nginx -t

![mkdir projectLEMP](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/b8ab3c94-e73a-44f1-b2ca-8accbeb3833a)

 We need to change the default Nginix host configured to run on the on Prt 80 by running 'sudo unlink /etc/nginx/sites-enabled/default' command and 
 
 then run '$ sudo systemctl reload nginx' command to reload Nginx and apply the changes you have made .

 To test the new server , we coppied the test below using sudo echo command  which is expected to reflect on the webpage by opening the website URL 
 
 using IP address:http://18.132.195.227:80
 
'sudo echo 'Hello LEMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s 

http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectLEMP/index.html'

 The below screen shots demonstrate the above explanation.

![UNLINK,RELOAD AND RUN PAGE](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/bce5dbb8-0388-4c86-8d41-beb33c376e7a)

URL access:http://18.132.195.227:80

![URL PAGE](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/ccdd0395-5b2c-43bf-b55f-ff8555904818)

## Step-5 Testing PHP with Nginx

in this step, you can do the testing by creating a test PHP file in this case its info.php using the nano editor by getting information a bout your 

server using URL. Later the file is removed as the web page generated has sensitve information about your server .

The first screen shot shows the commands run on git bash while the second screenshot is a demonstration of the server information from the web page.

![file edition with nanao and flie removal for security purposes](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/229b840f-a19a-4e87-8b23-afa59d0d903a)

![server info](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/97ccb5ee-51b2-4c1f-8dc9-81ec69da1d62)

## Step -6  Retriving data from MySQL.

First we need to connect MySQL to the root console after which we can noew run all the comands we need to by running the command '$ sudo mysql'

 We can now create a new database after which we create a new user for the database .See the screen shots below.

![create database](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/7b0865f4-34f2-4383-93cb-705e59854c25)

![create a new use plus grant permission](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/a0f7ab19-09f8-4099-8d35-18b8e5b9d522)

  The new user needs a password to allow only him to acess the database and make changes if to it and to end it all as the root user, you alspo need 
  
  to grant permission to the new user to acesss the database as shown above on the last command on the screenshot above.

 To confirm that the new user has access to the new database, we neend to get acess to the MYsql console created and by using the password created. 
 
  AFter that 
  
mysql> SHOW DATABASES; will give me the ouput below which will be demonstrated on the scren shot below.

![show database](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/76c7f947-e99e-4785-a75a-f813d364eb49)


 After that we can create a test table as shown below by typing  CREATE TABLE example_database.todo_list (item_id INT AUTO_INCREMENT,content 
 
 VARCHAR(255),PRIMARY KEY(item_id)); as below

 ![create a table](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/88d8f9da-ec0b-4ff0-8346-4a264b7c3133)


 mysql> INSERT INTO example_database.todo_list (content) VALUES ("My first important item"); will enable use insert a few rows into the test table 
 
 content 

![insert rows](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/8fcc2f3f-9a3b-4ab1-9514-4c514245af4e)
 

 to confirm the data was sucessfully saved we run mysql>  SELECT * FROM example_database.todo_list;only one row was inserted.

 ![select from example](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/e7a74aa7-7e23-460e-8cc0-e4ff34a6c1ca)


$ nano /var/www/projectLEMP/todo_list.php is a command used to connect MySQL database and querries the content of the to do list table and displays 

the list in a table 

Hence you can now access the to do list on the web as demonstrated below where only one row was inserted .

![to do url](https://github.com/NANA-2016/LEM--STACK-PROJECT/assets/141503408/55876ff3-df1e-45be-acaa-058882f34a0f)


#  * The End !!! *

 




















 

 













    

  
    



 


 


 


 

 

 
















 


 

 



















 





