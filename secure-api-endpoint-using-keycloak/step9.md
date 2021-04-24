# Expanding the access API to be secure
Keycloak utilizes the principles of Open-ID Connect (OIDC). This means that it is compatible with a large variety of security functions which follows this protocol. Flask has an internal module that comes with the basic Flask installation which is called OpenIDConnect, which we will use to secure the API.

<pre class="file" data-filename="project/api.py" data-target="insert" data-marker="# Flask API Secure Endpoint
# ... spoilers...">
# Flask Secure Endpoint (Requires Login)
@app.route("/secure")
@oidc.require_login
def secureEndpoint():
    loginInfo = oidc.user_getinfo(['preferred_username', 'email', 'sub'])
    username = info.get('preferred_username')
    email = info.get('email')
    user_id = info.get('sub')


# Flask Secure API Endpoint (Requires token to be provided)
@app.route("/api", methods=['POST'])
@oidc.accept_token(require_token=True, scopes_required=['basicUser'])
def secureTokenApi():
    return json.dumps({'hello': 'Welcome %s' % g.oidc_token_info['sub']})
</pre>