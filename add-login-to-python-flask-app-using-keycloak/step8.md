## Configuring the Python API to work with our Keycloak realm

# Adding a client_secrets.json file

When integrating Keycloak to work with a Flask API, it is usually convenient to have a `client_secrets.json` file which contains information about things like endpoints which the application will use to obtain and verify information. Let's create the file:

``
touch client_secrets.json
``{{execute T3}}

Below is how the json file should look, assuming you named the realm `myRealm`, and the client_ID as `flask-app`. Copy the code below into the `client_secrets.json` file:

```
{
    "web": {
        "issuer": "https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/auth/realms/myRealm",
        "auth_uri": "https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/auth/realms/myRealm/protocol/openid-connect/auth",
        "client_id": "flask-app",
        "client_secret": "",
        "redirect_uris": [
            "http://localhost:5000/*"
        ],
        "userinfo_uri": "https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/auth/realms/myRealm/protocol/openid-connect/userinfo", 
        "token_uri": "https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/auth/realms/myRealm/protocol/openid-connect/token",
        "token_introspection_uri": "https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/auth/realms/myRealm/protocol/openid-connect/token/introspect"
    }
} 
```

<!--
One final modification you will need to do is add the client secret, which can be found under Clients/ApiClient/Credentials in the Keycloak Admin console. You should take that value and replace the `SECRET HERE` value in the JSON file.
-->

<span style="color:red">Please note: If you used different names in for your realm/client, make sure to adjust the config file accordingly! If you get a json-related error from the api.py later, try repasting this code into the file.</span>


Now we will add some additional configurations to our Flask application. Open `api.py` in your editor again, and now we want to add the following configuration settings:

<pre class="file" data-filename="project/api.py" data-target="insert" data-marker="app = Flask(__name__)">
app = Flask(__name__)
app.config.update({
    'SECRET_KEY': 'NotVerySecretKey',
    'TESTING': True,
    'DEBUG': True,
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

This sets up the use of the `client_secrets.json` file we created just before, adds some additional configuration to the flask application and also initiates a new OpenIDConnect instance wrapped around our Flask application using `flask_oidc`.
