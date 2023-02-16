---
layout: default
#layout: archives
title: API request creation
icon: fas fa-archive
order: 4
---

<br />
<br />

# API REQUEST CREATION

Using Postman you will consume a WhoisXLMAPI endpoint to get the whois record of the domain - facebook.com
<br /><br />

## 1. Getting Authentication Key

Once logged in at WhoisXLMAPI:<br />
![One](../assets/img/num_1.png) Look for your username on the top right corner of the browser and click on it.<br />
![Two](../assets/img/num_2.png) Click on _My products_.

<div id="CopyKey"></div><br />

![Three](../assets/img/num_3.png) Copy your API key.<br /><br />
![Get API key](../assets/img/get_api_key_products.png)<br />

and then, <br />

![Copy API key](../assets/img/get_api_key.png)
<br /><br /><br />

## 2. Setting up the request environment

Log in Postman and create a new environment. **You can ether** <br />
![Four](../assets/img/num_4.png) On the left menu, select the option Environment <br />
![Five](../assets/img/num_5.png) Click on the **+** icon<br /><br />
![Create new environment](../assets/img/new_environment_B.png)<br />

**OR**

![Four](../assets/img/num_4.png) On the top menu, go to _My Workspace_ and click on the _New_ button.<br />
![Five](../assets/img/num_5.png) On the pop-up menu, select the option Environment<br /><br />
![Create new environment](../assets/img/new_environment_A1.png)<br />

and then, <br />

![Create new environment](../assets/img/new_environment_A2.png)
<br /><br />

![Six](../assets/img/num_6.png) Remember to name the environment you created. In this particular example, the environment has been called _API request_ <br />
![Create new environment](../assets/img/new_environment.png)

<br />

![Seven](../assets/img/num_7.png) Click on the **...** icon to set the environment you created as active environment <br />
![Create new environment](../assets/img/active_environment.png)

<br />

Within this new environment, **create a new variable** to save the API key that you [previously copied](#CopyKey). <br />

>  **Use variables to reuse values and protect sensitive data** <br /> Your API key is sensitive data; therefore, store it in variable type secret to keep its values masked on the screen.
{: .prompt-tip }

<br /><br />

### Environment variable creation
1. Within the environment you created **type the name** of your choosing for the variable that will store the API Key. In this particular example, the given name is _api_key_
2. Select the **type secret** to keep the value masked on the screen
3. **Paste the _API Key_** you already copied in [![Three](../assets/img/num_3.png)](#CopyKey) in the fields INITIAL VALUE and CURRENT VALUE
4. **Save environment** to keep the changes
![Create variable](../assets/img/variable.png)

<br /><br />

## 3. Consuming an API endpoint
Within _My Workspace_ look for the option Requests on the right menu. Select the **+** icon to **_Create new request_**

>  **The active environment should be one you created** <br /> As shown in ![Eight](../assets/img/num_8.png) for this particular example the active environment is _API request_. 
{: .prompt-warning }

![Create request](../assets/img/new_request.png)

<br />
You are ready to consume the WhoisXLMAPI endpoint to get the whois record of the domain - facebook.com

>  **The API endpoint to get is:** <br /> **GET** https://www.whoisxmlapi.com/whoisserver/WhoisService?apiKey=API_KEY&domainName=DOMAIN
{: .prompt-info }

You must provide two params: 
- **apiKey:** which is ready in the environment variable (called _api_key_ in this example) 
- **domainName:** which is facebook.com

Additionally, another parameter can be send:
- **outputFormat**: which is JSON to get the response in a JSON format. By default, the response is given in XML format.

Type the get endpoint call. Since you are consuming the endpoint it must be a GET call:
```
https://www.whoisxmlapi.com/whoisserver/WhoisService?
```

![Endpoint_call](../assets/img/api_call.png)

<br />

In the Params tab populate the first Query Params as follows:
- **KEY:** apiKey
- **VALUE**: type **{** to access the dropdown list and select the environment variable that contains the _API key_
![Param_apiKey](../assets/img/key.png)

<br />

Keep populating the rest Query Params as follows:
- **KEY:** apiKey
- **VALUE**: type **{** to access the dropdown list and select the environment variable that contains the _API key_ <br />
  ![Params](../assets/img/params.png)

<br />

![Nine](../assets/img/num_9.png) Last step: Follow the Postman suggestion ![Click_send](../assets/img/send.png) by click on the blue Send button on the top right.

<br />

The Status:200 OK means that the request was successful. You must see the response in JSON format: <br />
![Param_apiKey](../assets/img/response.png)

<br />

You can save your request knowing that is working:
![Save_request](../assets/img/save_request.png)

<br /><br />
