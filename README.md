# **Deploying a NodeJS application on Cloud, AWS EC2 Instance.**

This project is to host a NodeJS application written using Javascript on an EC2 Instance. 

## **Setting up project environment** 

Initializing EC2 Instance. 

Log into AWS console using IAM User account. 
Create an EC2 instance
Select an OS image - Ubuntu
Create a new key pair with any name & download .pem file
Use the same key pair in the EC2 instance creation screen. 
Instance type - t2.micro
Connecting to the instance using ssh

Use the below command to connect to EC2 instance using SSH

```
ssh -i <keypair_name>.pem ubunutu@<IP_ADDRESS>
```

## **Configuring Ubuntu on EC2 instance and installing dependencies**

Update the outdated packages and dependencies. 

```
sudo apt update
```

Installing Git. 

Install git using the below command. 

```
sudo apt install git
```

Installing NodeJS

```
sudo apt update
sudo apt install nodejs
sudo apt install npm
```


## **Cloning source code into Ubuntu EC2 instance**

To obtain the source code, use the below git command to clone the git repository. 

```
git clone https://github.com/praveendhas-gv/MyNodeJSApp.git
```

This will download all the contents of the repository MyNodeJSApp and store it in the EC2 instance in the present working directory.

 
## **Running the application using npm**

Before running the application, the dependencies for the program need to be installed through the below command. 
When executing the command, you would need to be inside the folder MyNodeJSApp 

```
npm install 
```
After the dependencies are installed, the application is run using the following command. 
```
npm run start
```

## **Accessing the application**

The application is set to listen on port 3000 as mentioned in app.js file. 
The application can be accessed through the below link  

```
http://<ec2-instance-public-ip>:3000/
```

NOTE - We will have to edit the inbound rules in the security group of our EC2, in order to allow traffic from our particular port

