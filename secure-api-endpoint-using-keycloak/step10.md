# Adding the secure endpoint
Keycloak utilizes the principles of Open-ID Connect (OIDC). This means that it is compatible with a large variety of security functions which follows this protocol. Flask comes with the basic installation which is called OpenIDConnect, which we will use to secure the API.

Additionally, lets add an endpoint called /secureapi, which will require an access token provided by the Keycloak server in order to authenticate.

<pre class="file" data-filename="project/api.py" data-target="insert" data-marker="# Flask Secure Endpoint">
# Flask Secure API Endpoint (Requires token to be provided)
@app.route("/secureapi", methods=['POST'])
@oidc.accept_token(require_token=True, scopes_required=['basicUser'])
def secureTokenApi():
    return json.dumps({'hello': 'Welcome %s' % g.oidc_token_info['sub']})
</pre>

Note that we specified that we are only allowed to do POST requests. By default, curl performs a GET request. If you try doing the same curl command against the new /secureapi endpoint, you will simply get an error.

> curl http://localhost:5000/secureapi

If we modify it to instead performs a POST request, we get an entirely different error:

> curl -X POST http://localhost:5000/secureapi

While our method is correct, this endpoint now requires an access token from our Keycloak server. Keycloak has a specific endpoint in mind for this, which is the *token_url* in the client_secrets.json we wrote, namely this:

> https://[[HOST_SUBDOMAIN]]-5000-[[KATACODA_HOST]].environments.katacoda.com/auth/realms/myRealm/protocol/openid-connect/token

So now we may take this endpoint and perform a curl request to it. It will require a few data headers, namely:
* *username* (name of the user you created, **=testuser**)
* *password* (password of the user you created **=password**)
*  grand_type (what type of authentication we are using for obtaining our token. In this case we are providing a password, so **=password**)
*  *client_id* (name of the client, **=flask-app**)
*  *client_secret* (the client secret we have worked with earlier)

We will additionally need to specify a header (H) of the type *Content-Type: application/x-www-form-urlencoded*. 
Let us now query the endpoint and obtain a token, and export it for use:

```
export TOKEN=$(curl -X POST 'https://[[HOST_SUBDOMAIN]]-5000-[[KATACODA_HOST]].environments.katacoda.com/auth/realms/myRealm/protocol/openid-connect/token' \
 -H "Content-Type: application/x-www-form-urlencoded" \
 -d "username=testuser" \
 -d 'password=pass' \
 -d 'grant_type=password' \
 -d 'client_id=flask_app' \
 -d 'client_secret=YOUR_SECRET_HERE' \
 | jq -r '.access_token')
```{{execute T3}}

Replace the **YOUR_SECRET_HERE** with the client secret you obtained earlier. After performing this, you may view the access token:

> echo $TOKEN

We may use this now to access the flask-api endpoint */secure*

curl -X POST http://localhost:5000/secure -H 'content-type: application/json' -H "Authorization: Bearer "$TOKEN
