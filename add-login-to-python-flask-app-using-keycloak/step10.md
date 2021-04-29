# Login redirect

Now lets try it out: Try heading to the address of the secure api on port 5000 in your web browser (you can technically query it in the terminal too using curl, but you will simply get a redirect attempt as HTML code):
> https://[[HOST_SUBDOMAIN]]-5000-[[KATACODA_HOST]].environments.katacoda.com/secure

I

You will notice that we actually end up on the Keycloak login page. Here you can use your Keycloak username and password which you defined earlier when you set up the server. Once you login, you should see the message from the `/secure` endpoint!

<span style="color:red">Please note: In case you receive the message *Connecting to Port X*, your Flask application has likely gone down and you need to restart it again in `Terminal 1`! CTRL+C tries to terminate it, and `python3 api.py` restarts it. The reason for it going down is from our changes to the file over the course of the tutorial.</span>

