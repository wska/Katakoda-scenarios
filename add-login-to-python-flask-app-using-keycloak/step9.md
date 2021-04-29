# Adding the login redirect endpoint

In this step we will not be securing our app endpoint by redirecting a user to an authentication provider (Keycloak server). This is a well suited to things like websites which are meant to be interacted with through a browser. 

Another way is by using an access token which is obtained from the Keycloak server, which are more suited for APIs which are not really interacted with through a browser. However in this tutorial we will be focusing on a login redirect here. 

This is actually quite straightforward to do in Flask. `flask_oidc` provides a set of security features which incorporates the OIDC protocols in a way that follows the flask syntax of endpoints.

In our instance, we will be using the the following:

> @oidc.require_login

Which configures the endpoint to require the user to log in using Keycloak, where you will need to provide a username and a password in order to access it, lest you [shall not pass](https://i.imgur.com/QV7ni6j.png).

Lets add a new endpoint, called `/secure` which will require a complete login procedure:

<pre class="file" data-filename="project/api.py" data-target="insert" data-marker="# Flask Login Redirect">
# Flask Login Redirect
@app.route("/secure")
@oidc.require_login
def secureEndpoint():
    return "Hello from our secure endpoint, where you will need to authenticate beforehand."
</pre>

