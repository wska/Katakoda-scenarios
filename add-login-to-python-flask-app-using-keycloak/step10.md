# Adding the login redirect endpoint

Securing an endpoint is to do so by redirecting a user to an authentication provider, such as our Keycloak server. This is a bit more suited to things like websites which are meant to be interacted with through a browser. 

Another way is by using an access token which is obtained from the Keycloak server. There are plenty of other tutorials that showcases how to do this, so we will be focusing on a login redirect here. 

This is actually quite straightforward to do in Flask. flask_oidc provides a set of security features which incorporates the OIDC protocols in a way that follows the flask syntax of endpoints.

In our instance, we will be using the the following:

> @oidc.require_login

Which makes it so that the endpoint will require the user to log in using Keycloak, where you will need to provide a username and a password in order to access it, lest you [shall not pass]().

Lets add a new endpoint, called `/secure` which will require a complete login procedure:

<pre class="file" data-filename="project/api.py" data-target="insert" data-marker="# Flask Login Redirect">
# Flask Secure Endpoint (Requires Login)
@app.route("/secure")
@oidc.require_login
def secureEndpoint():
    loginInfo = oidc.user_getinfo(['preferred_username', 'email', 'sub'])
    username = info.get('preferred_username')
    email = info.get('email')
    user_id = info.get('sub')
</pre>

