# Creating a client

<span style="color:red">Note: You can click the images to enlarge them</span>

Finally, we are going to create what is so called a *client*. Clients are entities that may request authentication of a user, either in the form of a access token or to provide other forms of credentials, such as a username and password. We are going to be creating a *confidential* client which will utilize the OpenID Connect authentication protocol, which is built ontop of the OAuth 2.0 framework. 

There are a couple of different types of clients which are provided by Keycloak:

* Confidential
* Public
* 

Navigate to `Clients` under your realm, and then press Create in the top right corner.
<img src="https://github.com/wska/Katakoda-scenarios/blob/main/secure-api-endpoint-using-keycloak/img/10.png?raw=true" width="500">

Let us call our new client flask-app. The flask application is on port 5000 unless you changed it, so make sure to also add the address **http://localhost:5000/** as the root URL. 

<img src="https://github.com/wska/Katakoda-scenarios/blob/main/secure-api-endpoint-using-keycloak/img/11.png?raw=true" width="500">

The client will be initialized as a *public client*. There are two things here which we will need to modify:

1. **Access type**. Swap it from *public* to *confidential*.
2. **Valid Redirect URls**. Here you will need to put it as *https://[[HOST_SUBDOMAIN]]-5000-[[KATACODA_HOST]].environments.katacoda.com/* due to the nature of our remote Katacoda environment host. if any application which does not follow the above URl tries to connect to this client, it will be blocked. This is for security reasons, so not just anyone may try to authenticate towards the client.

Finally, there is one last thing we are going to need to extract from here, which is the *client secret*. After making the changes above, you can go ahead and save your changes by clicking the *save* button at the bottom of the page. When you now toggle from a *public* to a *confidential* client, a *credentials* tab will show up at the top. If you head on over there, you will notice a field called *client secret*. 

<img src="https://github.com/wska/Katakoda-scenarios/blob/main/secure-api-endpoint-using-keycloak/img/13.png?raw=true" width="500">

You are going to need this secret to configure the flask application, so you can keep this tab open. You do not need to make any other changes in Keycloak.