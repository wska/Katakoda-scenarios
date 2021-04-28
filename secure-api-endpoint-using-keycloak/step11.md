# Login redirects

Now lets try it out: Try heading to the address of the secure api on port 5000:
> https://[[HOST_SUBDOMAIN]]-5000-[[KATACODA_HOST]].environments.katacoda.com/secure


You will notice that we actually end up on the Keycloak login page. Here you can use your Keycloak username and password which you defined earlier when you set up the server. Once you login, you should see the message from the */secure* endpoint!

There are many more different security and authentication methods available for *flask_oidc*. If you are interested, you can read more on the official documentation here:

> https://flask-oidc.readthedocs.io/en/latest/


