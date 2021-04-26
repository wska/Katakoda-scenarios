

Note that we specified that we are only allowed to do POST requests. By default, curl performs a GET request. If you try doing the same curl command against the new /secureapi endpoint, you will simply get an error.

> curl http://localhost:5000/secureapi

If we modify it to instead performs a POST request, we get an entirely different error:

> curl -X POST http://localhost:5000/secureapi

While our method is correct, this endpoint now requires an access token from our Keycloak server.

> https://[[HOST_SUBDOMAIN]]-5000-[[KATACODA_HOST]].environments.katacoda.com/secure"