# Linux Server Configuration - Udacity Project
## Get your server.✅ 
1. Start a new Ubuntu Linux server instance on Amazon Lightsail. There are full details on setting up your Lightsail instance on the next page.

![](img/instance2.png)

2. Follow the instructions provided to SSH into your server. ✅ 
   
```sh
ssh -i ~/.ssh/lightsail.rsa -p 2200 ubuntu@18.195.254.152
```

## Secure your server.
3. Update all currently installed packages. ✅ 

![](img/update2.png)

4. Change the SSH port from 22 to 2200. Make sure to configure the Lightsail firewall to allow it. ✅ 

![](img/port220.png)

5. Configure the Uncomplicated Firewall (UFW) to only allow incoming connections for SSH (port 2200), HTTP (port 80), and NTP (port 123). ✅ 

![](img/ufw2.png)

## Give grader access.
In order for your project to be reviewed, the grader needs to be able to log in to your server.

6. Create a new user account named grader. ✅ 

![](img/add-user.png)


7. Give grader the permission to sudo. ✅ 

![](img/add-user2.png)

8. Create an SSH key pair for grader using the ssh-keygen tool. ✅ 

```sh
ssh -i ~/.ssh/grader-key -p 2200 grader@18.195.254.152
```

(The passphrase is: udacity)

## Prepare to deploy your project.
9. Configure the local timezone to UTC. ✅

![](img/utc2.png)

10. Install and configure Apache to serve a Python mod_wsgi application. ✅ 

```sh
sudo apt-get install apache2
```

11. Install and configure PostgreSQL:

Do not allow remote connections ✅ 


![](img/database.png)

Create a new database user named catalog that has limited permissions to your catalog application database. ✅ 

![](img/catalog-db.png)

12. Install git. ✅ 

![](img/install-git.png)

## Deploy the Item Catalog project. ✅ 

13. Clone and setup your Item Catalog project from the Github repository you created earlier in this Nanodegree program. ✅ 

14. Set it up in your server so that it functions correctly when visiting your server’s IP address in a browser. Make sure that your .git directory is not publicly accessible via a browser! ✅ 
(Public IP is: http://18.195.254.152// or http://ec2-18-195-254-152.eu-central-1.compute.amazonaws.com/)

## Sources
Udacity forum: https://discussions.udacity.com/
Udacity Linux Server Course: https://www.udacity.com/course/full-stack-web-developer-nanodegree--nd004
Digital Ocean: https://www.digitalocean.com/community/questions/how-do-i-remove-apache2-ubuntu-default-page
Stack Overflow: https://stackoverflow.com/

