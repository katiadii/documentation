# IIS server configuration for EspoCRM

These instructions are supplementary to the [server configuration](server-configuration.md) guidelines. Note, that all configuration settings listed here are made on Windows Server 2019.

## To install EspoCRM on IIS server, you need to follow these steps:

1. Install **IIS server** and **Web Platform Installer**.

2. Install **PHP** (version 7.3 and later) with **Web Platform Installer**.

3. Install **MySQL** (version 5.7 and later) either with **Web Platform** or **MSI Installer**. 

4. Download **phpMyAdmin**, create a database and user account.

5. Download the latest version of EspoCRM and go to the `/PATH_TO_ESPO/`, for example `/localhost/instances`.

Note, that `/PATH_TO_ESPO/` should be changed to the absolute path of the EspoCRM instance on your server. It can be `C:\inetpub\wwwroot` if you exctracted EspoCRM package to the default IIS root directory.

# Troubleshooting

If some of these errors occur, then you should follow the next tips:

## 1. Internal Server Error
![image](https://user-images.githubusercontent.com/88880212/139695451-a4b56e3f-9003-4939-8d5f-3a5e4683f103.png)

- Add these lines to the `web.config` file that is located in the EspoCRM folder:

**`<remove fileExtension=".json" />`**

**`<remove fileExtension=".woff" />`**


- Then, it will look like this:


![image](https://user-images.githubusercontent.com/88880212/139696857-337c3806-e7d8-4ed8-9516-f2987cd227f0.png)

- After, save the file and refresh the page in the web browser.


## 2. This page isn't working
![image](https://user-images.githubusercontent.com/88880212/139696966-b9b455cd-22c5-4b3e-b9ac-066af15263aa.png)

- Go to the `/PATH_TO_ESPO/`, 
for example, `C:\inetpub\wwwroot\instances` . After this click on the folder with EspoCRM files (e.g. Instances) > Properties > Security > IIS and EspoCRM\Users, choose Full control > Allow > Apply.

![image](https://user-images.githubusercontent.com/88880212/139697111-bf6c6dbf-f59f-47d0-baf5-6c3aa0e3a9b8.png)

- Then refresh the page and install EspoCRM:

![image](https://user-images.githubusercontent.com/88880212/139697203-34882c2b-06e7-4ffe-b242-d7136393a9da.png)



