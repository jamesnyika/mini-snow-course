# Chapter 2 - Setup For application

### Pre-requisites

#### 1- ServiceNow Instance
To take this class you will require a ServiceNow instance. An instance is a running ServiceNow application. Fortunately for development purposes, ServiceNow offers free instances for development and experimentation at :

[ServiceNow Developer Site](http://developer.servicenow.com)

Once you signup and provide a username and password, you will receive credentials in the email you have provided. These credentials are for the developer program. Once inside - go to the "Manage" menu item and you can then REQUEST an instance.

Please request an Instance. Release is immaterial at this point.

Once completed, you will have received an instance link that will not be reclaimed provided you keep your instance accessed at least every 10 days or so.


#### 2- Javascript Knowledge
You will need to obtain such an instance before taking this course as well as get some rudimentary understanding of javascript. The link below is to a basic javascript course on YouTube. Use this course to quickly understand the basic syntax of the language.

[A Basic Javascript Course](https://www.youtube.com/watch?v=vEROU2XtPR8)

#### 3- Source Control - Github
You will need a repository to store your application. Go to [Github](http://www.github.com) and create an account for yourself. Once there, follow the instructions on how to create a repository. *NB: Create the repository without a README.md  or license file. These are check off options at the bottom the form*. You may name the repository anything you like. Once created, you will need the HTTP url of the respository (not SSH) and your username password to be able to perform step 4.

#### 4-ServiceNow Studio
The last pre-requisite is to set up a blank project in ServiceNow for your application.  Once logged into ServiceNow, take the following steps

1. Type 'Studio' in the filter navigation window
2. Select the Studio option to open Studio
3. Select 'Create New Application' to create a blank application from scratch.
4. In the top level menu for Studio, select 'Link to Source Control'
5. Fill in the URL, username and password from step 3 above. You now have linked your application to the respository. You will now be able to commit changes to the repository as you make progress with your application.

### Scoped Applications
What you have now created is a scoped application. This means this application resides in its own container with all artifacts we will create, fully maintained inside the application.

Next we will describe the requirements for the application we will be building.

[Next - Chapter 3](https://github.com/jamesnyika/motivf-snow/blob/master/chap3/README.md)
