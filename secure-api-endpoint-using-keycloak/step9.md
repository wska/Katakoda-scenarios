## Configuring the Python API to work with our new Keycloak realm

# Adding a client_secrets.json file
When integrating Keycloak to work with a Flask API, it is usually convenient to have a client_secrets JSON file which contains information about things like endpoints which the application will use to obtain and verify information. Here is how the json file should look, assuming you named the realm myRealm, and the client_ID as flask-app. 
<pre class="file" data-filename="project/client_secrets.json" data-target="replace">
{
    "web": {
        "issuer": "https://[[HOST_SUBDOMAIN]]-5000-[[KATACODA_HOST]].environments.katacoda.com/auth/realms/myRealm",
        "auth_uri": "https://[[HOST_SUBDOMAIN]]-5000-[[KATACODA_HOST]].environments.katacoda.com/auth/realms/myRealm/protocol/openid-connect/auth",
        "client_id": "flask-app",
        "client_secret": "SECRET HERE",
        "redirect_uris": [
            "http://localhost:5000/*"
        ],
        "userinfo_uri": "https://[[HOST_SUBDOMAIN]]-5000-[[KATACODA_HOST]].environments.katacoda.com/auth/realms/myRealm/protocol/openid-connect/userinfo", 
        "token_uri": "https://[[HOST_SUBDOMAIN]]-5000-[[KATACODA_HOST]].environments.katacoda.com/auth/realms/myRealm/protocol/openid-connect/token",
        "token_introspection_uri": "https://[[HOST_SUBDOMAIN]]-5000-[[KATACODA_HOST]].environments.katacoda.com/auth/realms/myRealm/protocol/openid-connect/token/introspect"
    }
} 
</pre>
One final modification you will need to do is add the client secret, which can be found under Clients/ApiClient/Credentials in the Keycloak Admin console. You should take that value and replace the "SECRET HERE" value in the JSON file.

</br>
</br>

<span style="color:red">Note: If you used different names in for your realm/client, make sure to adjust the config file accordingly!</span>

</br>
</br>

Now we will add some more configuration to our Flask app. Back to *api.py*, we want to add the following settings:
<pre class="file" data-filename="project/api.py" data-target="insert" data-marker="# Flask settings">
# Flask settings
app = Flask(__name__)
app.config.update({
    'SECRET_KEY': 'NotVerySecretKey',
    'TESTING': True,
    'OIDC_CLIENT_SECRETS': 'client_secrets.json',
    'OIDC_ID_TOKEN_COOKIE_SECURE': False,
    'OIDC_REQUIRE_VERIFIED_EMAIL': False,
    'OIDC_USER_INFO_ENABLED': True,
    'OIDC_OPENID_REALM': 'myRealm',
    'OIDC_SCOPES': ['openid', 'email', 'profile'],
    'OIDC_INTROSPECTION_AUTH_METHOD': 'client_secret_post'
})

oidc = OpenIDConnect(app)

</pre>

This sets up the use of the *client_secrets.json* file we created just before, and also initiates a new OpenIDConnect application wrapped around our Flask app.
