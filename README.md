# Linux Server Configuration - Udacity Project
## Get your server.
1. Start a new Ubuntu Linux server instance on Amazon Lightsail. There are full details on setting up your Lightsail instance on the next page.c

![](img/instance.png)

2. Follow the instructions provided to SSH into your server. ✅ 
   
```sh
ssh -i ~/.ssh/LinuxServerProjectUdacity.rsa -p 2200 ubuntu@35.177.166.212
```

## Secure your server.
3. Update all currently installed packages. ✅ 

![](https://photos-1.dropbox.com/t/2/AADkGbaAJ_uzmETEmvf3Qs4tCfNRzgMlZJKb2-7VCEJUsQ/12/369982627/png/32x32/1/_/1/2/Captura%20de%20pantalla%202017-12-12%20a%20las%2019.33.20.png/EMXso_YCGOEEIAcoBw/KLT-4eBLW3mmfFNneR5vrxiKuvDtmGaMtBkjT3nOFRw?preserve_transparency=1&size=1280x960&size_mode=3)

![](https://photos-2.dropbox.com/t/2/AABDdb3A3iuh9IML059cxZFe0mMuU3ScPIkoy7BeOb2wnA/12/369982627/png/32x32/1/_/1/2/Captura%20de%20pantalla%202017-12-12%20a%20las%2019.58.39.png/EMXso_YCGOoEIAcoBw/hNTxJZEzILH4hoMCSrhGLyQ6ml2z_yzW2WzD8U99dQ0?preserve_transparency=1&size=1280x960&size_mode=3)

4. Change the SSH port from 22 to 2200. Make sure to configure the Lightsail firewall to allow it. ✅ 

![](https://photos-2.dropbox.com/t/2/AABdktKskPt2Nr47NYpWU_uN-Dfy9mk526dth5IyXhilJg/12/369982627/png/32x32/1/_/1/2/Captura%20de%20pantalla%202017-12-12%20a%20las%2019.38.37.png/EMXso_YCGOIEIAcoBw/-cTgy88te2xUpifQWxHuNdyc-_ZTbGTA3hd4hptpTMk?preserve_transparency=1&size=1280x960&size_mode=3)

5. Configure the Uncomplicated Firewall (UFW) to only allow incoming connections for SSH (port 2200), HTTP (port 80), and NTP (port 123). ✅ 

![](https://photos-6.dropbox.com/t/2/AACEdmMxbewdB14wVgM5hMYHHn-1KUcwm6GxHVNw3pNo_g/12/369982627/png/32x32/1/_/1/2/Captura%20de%20pantalla%202017-12-12%20a%20las%2019.16.11.png/EMXso_YCGN8EIAcoBw/n2XNpNuf6AYiO_gVYHVniR9EaKJhCek_0MTd8o91gcc?preserve_transparency=1&size=1280x960&size_mode=3)

## Give grader access.
In order for your project to be reviewed, the grader needs to be able to log in to your server.

6. Create a new user account named grader. ✅ 

![](https://photos-1.dropbox.com/t/2/AAACVBbSf8sFC-e3BxccdKmf-Vxe3mqTt0tdrjHcyxNrHg/12/369982627/png/32x32/1/_/1/2/Captura%20de%20pantalla%202017-12-11%20a%20las%2020.01.09.png/EMXso_YCGOUEIAcoBw/Z01tIxWu10uun6z9ORixicjkBGzzME3BXe0FgLbn2ic?preserve_transparency=1&size=1280x960&size_mode=3)


7. Give grader the permission to sudo. ✅ 

![](https://photos-3.dropbox.com/t/2/AACceJNx6LEr8ZfoE8W4QvyxhSYXQ1xfHqBzK1ZjtMPy2Q/12/369982627/png/32x32/1/_/1/2/Captura%20de%20pantalla%202017-12-11%20a%20las%2020.04.57.png/EMXso_YCGOkEIAcoBw/eKqogPDSSNHr0l26lXJCP64uLK9P5qjUBLPPhLioUU8?preserve_transparency=1&size=1280x960&size_mode=3)

![](https://photos-3.dropbox.com/t/2/AAC8jzVgW_Jd8w_2EXruV8beBP_J2XJY0VCoR7OvZwoIog/12/369982627/png/32x32/1/_/1/2/Captura%20de%20pantalla%202017-12-12%20a%20las%2019.41.58.png/EMXso_YCGOMEIAcoBw/1E5Ktfbexz_ZLEpld3Msh7YNthT5M8VqZ3WD75iDZuI?preserve_transparency=1&size=1280x960&size_mode=3)

8. Create an SSH key pair for grader using the ssh-keygen tool. ✅ 

```sh
ssh -i ~/.ssh/grader_key -p 2200 grader@35.177.166.212
```

Prepare to deploy your project.
9. Configure the local timezone to UTC. ✅

![](https://photos-1.dropbox.com/t/2/AADZ4zmEjmIwWvgy63FhGJTn_NHtueH3g53Mz9G4PBbd3A/12/369982627/png/32x32/1/_/1/2/Captura%20de%20pantalla%202017-12-12%20a%20las%2019.45.30.png/EMXso_YCGOQEIAcoBw/etC7-XtkPQXF86CpyjzF7VAMzcQJtqQmW56IwVWi1FA?preserve_transparency=1&size=1280x960&size_mode=3)

10. Install and configure Apache to serve a Python mod_wsgi application. ✅ 

```sh
sudo apt-get install apache2
```

11. Install and configure PostgreSQL:

Do not allow remote connections ✅ 


![](https://photos-6.dropbox.com/t/2/AAAwk8wJNTGtqwxTcFQkfzzpKgL1HhPQG6e1HOjGURVm4g/12/369982627/png/32x32/1/_/1/2/Captura%20de%20pantalla%202017-12-12%20a%20las%2019.49.59.png/EMXso_YCGOYEIAcoBw/zunfQrfytnGV2zmmmpfVBe0h3GZHlUgj_KibvtG-AAA?preserve_transparency=1&size=1280x960&size_mode=3)

Create a new database user named catalog that has limited permissions to your catalog application database. ✅ 

![](https://photos-2.dropbox.com/t/2/AACt3qkdWcFDoN1Qmb7HvPpa3Zm1IVPckzsRPlzo19jjQQ/12/369982627/png/32x32/1/_/1/2/Captura%20de%20pantalla%202017-12-12%20a%20las%2019.57.46.png/EMXso_YCGOcEIAcoBw/Z0LXGWs8RNDhYnjcjBLRcjfOGf2aLPyBu3Hw1HEf_Pc?preserve_transparency=1&size=1280x960&size_mode=3)

12. Install git. ✅ 

![](https://photos-4.dropbox.com/t/2/AACB-ZSZfngJPfiq-jsYf_naezXFnWTCSIocgaxD8jNmUg/12/369982627/png/32x32/1/_/1/2/Captura%20de%20pantalla%202017-12-12%20a%20las%2020.00.03.png/EMXso_YCGOgEIAcoBw/vuUG4dKDE9ynbXQZVp6FJzcN95ldpOBuIJjpsAO7PlI?preserve_transparency=1&size=1280x960&size_mode=3)

## Deploy the Item Catalog project. ❌ 

13. Clone and setup your Item Catalog project from the Github repository you created earlier in this Nanodegree program. ✅ 

14. Set it up in your server so that it functions correctly when visiting your server’s IP address in a browser. Make sure that your .git directory is not publicly accessible via a browser! ❌ 
(The public IP is: http://35.177.166.212/, but after configuring the server I only see the default Ubuntu page. I have tried several things but i can't resolve it)
