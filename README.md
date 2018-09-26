# Terjmat


## Overview
Terjmat is a multi-language translation integrated with Telegram application to make the translation easy by using IBM services. IBM's Language Translator is one of the best language translation service, it has the capability to connect to other IBM's services. These services can be linked to Telegram application by using Node-RED app. When you link them, users can use the translation in easy way by send text or voice to your bot. In this guide, we shall go through the steps involved in creating a Node-RED boilerplate available in IBM Cloud and link Telegram to a Telegram as the user interface using Node-RED flows in under 20 minutes by using only IBM Cloud services.
## Learning objectives
After completing this project, you will understand how to;
- Create a Node-RED flow
- Create a translator dialog using Language Translator, Speech to Text, Text to Speech IBM services.
- Integrate Node-RED with Telegram as an interface for Terjmat. 
## Prerequisites
In order to complete this project, you will need the following prerequisites:
- IBM Cloud account - sign up if you don't have an account yet.
- Language Translator service
- Speech to Text service
- Text to Speech service
- Node-RED starter
- Install Telegram Application on your Mobile Phone.

## Estimated time
- Creating a bot on Telegram should take less than 5 minutes
- Developing the complete application on Node-RED should take a maximum 20 minutes.
- Overall the time for completing this project should take approximately 25 minutes.
## Building the Translator flow
### Creating a Telegram bot
After installing Telegram on a mobile phone of your choice, search for "botFather".
![`Translator`](images/1.jpg)

Once found, send a /newbot command and follow these instructions:
- Set a name
- Set a username
- Save the access token for future use

<img src="images/2.jpg" width="50%" height="50%" display: block margin-left: auto margin-right: auto>


*Note: make sure to create all the requirement services this project before goes to next steps.

### Creating Node-RED
To creating and configuring Node-RED app, go to your IBM Cloud account click to Catalog then choice Starter Kits from the lift side then choice Node-RED Starter as shows in the following figure.

![`Translator`](images/3.png)



After that, Fill-out the fields to create IoT Platform:
- App name: has to be unique in the IBM cloud domain.
- Host name: will be filled out automatically based on the App name.

click on Create 
![`Translator`](images/4.png)

Then, wait some time until shows the application are Running and click on Visit App URL

![`Translator`](images/5.png)

After that, for first time, it will ask you to setup the username and password. Please follow the instruction to secure your editor so only authorized users can access it. 

<img src="images/6.png" width="50%" height="40%" >

Then, click on "Go to your Node-RED flow editor".

![`Translator`](images/7.png)

### Configure the Telegram 
Now, this is Node-RED editer and we need to add Telegram nodes, so select manage palette from the top right menu.

![`Translator`](images/8.jpg)

At the manage palette menu click on the Install tab then search for telegram. After that, install node-red-contrib-telegrambot and close the palette menu.

![`Translator`](images/9.png)

Search for telegram nodes from the upper left filter section then drag and drop Telegram receiver and Telegram sender nodes.  
![`Translator`](images/10.png)
Double click on the Telegram receiver node and click on the pencil icon for configuring your bot credentials

![`Translator`](images/11.png)

Fill the bot-name and token fields according to the bot credentials you created earlier.

![`Translator`](images/12.png)

In Telegram sender node select the bot credentials you created in Telegram receiver node (example_bot in my case).

![`Translator`](images/13.png)

Now you have configured the Telegram part on Node-RED. You can test it by connecting the Telegram receiver node to the Telegram sender node.

![`Translator`](images/14.png)

You can send a message to your bot on Telegram and it will echo the message you wrote. That's because we forwarded the message payload directly to the Telegram sender.

<img src="images/15.jpg" width="50%" height="40%" >

### Connecting IBM's services

Now the bot interface is connected to Node-RED and ready to use, let’s start integrating all the services with Npde-RED application. Go to the Node-RED application in IBM Cloud and click on the Connections tab on the lift side. Then click on Create connection
![`Translator`](images/16.png)

You will find all the application that you have created connect all the services that needed.
![`Translator`](images/17.png)

After that, restage the app to configure the new changes.

![`Translator`](images/18.png)

Copy the code form the Terjmat flow file and import them into Node-RED clipboard:


- [Terjmat flow](terjmat-flow.json)

Then, configure all these nodes; Speech to Text, Text to Speech, Language Translator, and Telegram.

Finally, your flow should look like the following figure. Click on Deploy button in the upper right
![`Translator`](images/19.png)




### Testing your application on Telegram.

<img src="images/15.jpg" width="50%" height="40%" >

## Summary
Node-RED can make things easier. In this project, you have created a translator with a Telegram interface. This is sample and basic, and it can be modified and enhanced in respect to your needs.
