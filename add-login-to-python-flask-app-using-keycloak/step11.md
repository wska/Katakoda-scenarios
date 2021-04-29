# Login redirect

Now lets try it out: Try heading to the address of the secure api on port 5000 in your web browser (you can technically query it in the terminal too using curl, but you will simply get a redirect attempt as HTML code):
> https://[[HOST_SUBDOMAIN]]-5000-[[KATACODA_HOST]].environments.katacoda.com/secure


You will notice that we actually end up on the Keycloak login page. Here you can use your Keycloak username and password which you defined earlier when you set up the server. Once you login, you should see the message from the */secure* endpoint!


