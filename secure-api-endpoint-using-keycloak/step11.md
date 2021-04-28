# Adding the login redirect endpoint

Another alternative way of securing an endpoint is to do so by redirecting a user to an authentication provider, such as our Keycloak server. This is a bit more suited to things like websites which are meant to be interacted with through a browser. 

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

