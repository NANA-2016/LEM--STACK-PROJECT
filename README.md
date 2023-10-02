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













 





