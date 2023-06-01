**Sample code to create Azure Function App in IntelliJ Idea**

1-FirstFunction --- HTTP Trigger 

2-SecondFunction---- HTTP Trigger, Blob Output Binding

Pre Requisites :- 

1) Azure CLI on your OS and Azure ToolKit plugin installation to your IDE. 

2) Various ways to create a function app and below are a few of them(there are a lot others too) -  

A-->Using maven commands - Follow this simple official doc  - https://learn.microsoft.com/en-us/azure/azure-functions/create-first-function-cli-java?tabs=bash%2Cazure-cli%2Cbrowser -- It will create a pom for you


B--> Using IntelliJ Idea - Follow this doc--- https://learn.microsoft.com/en-us/azure/azure-functions/functions-create-maven-intellij


C--> Else create a simple maven project and create a normal class and copy the required triggers structure from azure -- https://learn.microsoft.com/en-us/azure/azure-functions/functions-triggers-bindings?tabs=java

**I followed step B,C and it was easy, faced bit difficulty in A.**


After following any of the steps we will be getting a class with @FunctionName and some sample code.
host.json, local.settings.json if not created then create similar to the one in this repo.

local.settings.json - is for local development
host.json -- function app configurations
in the local.settings.json populate your respective storage account value.


3) To run in local we can run via maven commands

**mvn clean install**

Beforing running one particular function, better to comment entirely the function class or the other function code as I faced some trouble. Only keep the funtion you want to run.

**mvn azure-functions:run**

4) Other way is to simply click the run button on the IDE

5) Test in local using the endpoint which gets logged in console

6) After successful testing, create a function app in the portal
7) Right Click on the project on IDE -----> Azure ----> Deploy to Azure Functions

8) A small window with various details like to login, subcription selection, function app selection etc.

9) Find your function app and click on apply and ok and wait for the deployment to be comepleted.

10) If deployment is success, we can see the 2 functions created in our azure function app in portal with 2 diffent HTTP trigger functions
