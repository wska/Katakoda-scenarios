# Creating a client

Finally, we are going to create what is called a *client*. Clients are entities that may request authentication of a user, either in the form of a access token or to provide other forms of credentials, such as a username and password. 

There are a couple of different types of clients which are provided by Keycloak:

* Confidential
* Public
* Bearer only

These types have their different usages depending on the application type. We will be using a public client, which is the default when creating a new one.

Navigate to `Clients` under your realm, and then press `Create` in the top right corner:

<img src="https://github.com/wska/katacoda-scenarios/blob/main/add-login-to-python-flask-app-using-keycloak/img/10.png?raw=true" width="500">

Let us call our new client Flask application. The Flask application is on port 5000 unless you changed it, so make sure to also add the address **http://localhost:5000/** as the root URL:

<img src="https://github.com/wska/katacoda-scenarios/blob/main/add-login-to-python-flask-app-using-keycloak/img/11.png?raw=true" width="500">

The client will be initialized as a *public client*. There is one thing here we need to modify, which is the **Valid Redirect URls**. Here you will need to put it as:

>*http://[[HOST_SUBDOMAIN]]-5000-[[KATACODA_HOST]].environments.katacoda.com/*\* 

This is due to the nature of our remote Katacoda environment host. If any application which does not follow the above URl tries to connect to this client, it will be blocked. This is for security reasons, so not just anyone may try to authenticate towards the client.

<!--
Finally, there is one last thing we are going to need to extract from here, which is the *client secret*. After making the changes above, you can go ahead and save your changes by clicking the `Save` button at the bottom of the page. When you now toggle from a *public* to a *confidential* client, a *credentials* tab will show up at the top. If you head on over there, you will notice a field called *Secret*:

<img src="https://github.com/wska/katacoda-scenarios/blob/main/add-login-to-python-flask-app-using-keycloak/img/13.png?raw=true" width="500">

You will need this secret to configure the Flask application, so you can keep this tab open. You do not need to make any other changes in Keycloak. The client secret is generated, and you can can also generate new ones from here. 
-->
Just a few steps left now, [keep going](https://64.media.tumblr.com/3487d11245609f74cb81c7e67c49bac5/tumblr_npnnnwNWJq1qc4uvwo1_500.jpg)!
