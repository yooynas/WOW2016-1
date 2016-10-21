# WOW2016

## Simplify Your Life with Your Own IBM Watson Personal Assistant
We all lead busy lives, so it can be a challenge to find timely and relevant information. But what if you had a personal assistant to deliver this for you? In this lab, you will build your own cognitive cloud app powered by IBM Watson to deliver news and weather customized for your preferences and location. You will build your own Node.js application deployed to IBM Bluemix and use services from the Watson Alchemy News and the Weather Company. News articles are analyzed for category and sentiment and a real-time weather forecast is delivered for your location. Your assistant will speak to you with Watson text-to-speech technology, or can tweet your report. In the process, you will also learn more about Node-RED, Node.js and Bluemix.

### Technology Overview
![codecamp16](https://cloud.githubusercontent.com/assets/12015008/19007253/c430234c-8718-11e6-8ff9-a328229e018a.png)

### Application Flow
<img width="1059" alt="flow" src="https://cloud.githubusercontent.com/assets/7436221/19576366/9ae31918-96c7-11e6-8d7d-4c14e2857df1.png">

## Setup Instructions

1. Create a bluemix account on https://console.ng.bluemix.net/

2. Create a uniques name of your organization and space to your application in it.

3. Click on catalog to get various options of boilerplate code. Select Node-RED.

<img width="1180" alt="Landing" src="https://cloud.githubusercontent.com/assets/7436221/19538326/60742c00-9608-11e6-897b-9efd7ba25a22.png">

..Name the app.
..Select a **web** application.

<img width="1176" alt="select node-RED" src="https://cloud.githubusercontent.com/assets/7436221/19538333/64ce84f8-9608-11e6-9b94-9b3249c8819b.png">

- Your application will start staging and will start. The app will have cloudant database by default to store node red metadata.

<img width="1140" alt="view app" src="https://cloud.githubusercontent.com/assets/7436221/19539588/fdc0d926-960e-11e6-9b97-0ed1d4c4f51a.png">








- Select **Overview** tab on the left to see the detailed view of your application. 


<img width="1143" alt="overview" src="https://cloud.githubusercontent.com/assets/7436221/19539543/c21fc422-960e-11e6-9cae-0825da0431a8.png">

As we are going to make our own assistance. We can enable it to notify us the temperature/weather of any place on the earth.
For that we need to add a service to this app, which is called "Weather Company Data". So we select Add a service or API button.
 
 <img width="669" alt="screen shot 2016-09-30 at 5 46 53 pm" src="https://cloud.githubusercontent.com/assets/7436221/19010514/3082de1e-8736-11e6-9216-b96b7d2bfae4.png">

It will create in few minutes and link itself to the existing app.
Now your App has to be **Restaged** to reflect the updation.

- Go back to overview of your App and add another service called "Text to Speech" and restage the application.

- Click on the link of your application. You will be taken to **NODE-RED**
..Here, you can enter into Node-RED Editor to start making flows.
Creating flows makes life easier with just dragging and dropping the functional nodes having code or API calls.
It helps in debugging at each level as well so you know where the bug is located.

<img width="1145" alt="screen shot 2016-09-30 at 3 22 06 pm" src="https://cloud.githubusercontent.com/assets/7436221/19008682/c2fab772-8721-11e6-9c58-6dd0d8ebde3e.png">

Left panel gives a vast range of nodes to drag and connect. This helps to perform functions and make an application running in minutes.


<img width="1147" alt="screen shot 2016-09-30 at 3 23 58 pm" src="https://cloud.githubusercontent.com/assets/7436221/19008712/0cb77328-8722-11e6-8489-6cd007d4ef2f.png">

Three files are added into this github repository. Create three flows.
- Import [Main Flow](main.json)
- Import [Weather Flow](weather.json)
- Import [News Flow](news.json) 

<img width="533" alt="screen shot 2016-09-30 at 5 31 54 pm" src="https://cloud.githubusercontent.com/assets/7436221/19010403/425c31fa-8734-11e6-9442-69010121a7d2.png">

Copy each flow from the github file to create flows on you node-red and paste here.

A couple more steps are requrired to get the application up and running. First click on the "text to speech" node and select "US English"

![](https://cloud.githubusercontent.com/assets/8397737/19015255/ab039ce4-87b5-11e6-865b-7a7c26b3c2eb.png)

<img width="494" alt="screen shot 2016-09-30 at 6 17 16 pm" src="https://cloud.githubusercontent.com/assets/8397737/19015276/0a02475e-87b6-11e6-866d-8892ab17b39d.png">

The "name" field can be left blank. Finnally, click on the each link node on the main tab:


<img width="174" alt="screen shot 2016-10-01 at 8 57 21 am" src="https://cloud.githubusercontent.com/assets/8397737/19015290/3f16b920-87b6-11e6-96d5-1412e6451f75.png">

and connect to the proper recieve node:

<img width="500" alt="screen shot 2016-10-01 at 9 06 17 am" src="https://cloud.githubusercontent.com/assets/8397737/19015294/57df73e8-87b6-11e6-91bc-0e5a41068ffa.png">

"Outgoing weather" should connect to "Incomming weather" and "Outgoing news" should connect to "Incomming news"

## Speech to text Microphone application
- We are using another bluemix application to record our message and send it to our node-red app. Check the link below.
```
https://wow-mic.mybluemix.net/
```

Enter your application link in the text box shown. 
<--host name-->.mybluemix.net

And record your message like
```
**What is the current weather in Chicago.**
```
Upload your message and it makes a call to your Node-RED backend application and speaks out the result.




