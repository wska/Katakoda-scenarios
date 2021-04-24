# Starting up Keycloak

Since we pulled the Docker image earlier during Step 1, we can now launch the Keycloak server using docker. Open a new terminal windows and input:


```
docker run -p 8080:8080 -e PROXY_ADDRESS_FORWARDING=true -e KEYCLOAK_USER=admin -e KEYCLOAK_PASSWORD=admin quay.io/keycloak/keycloak:12.0.4
```{{execute}}

This starts the Keycloak docker image and insert a basic administrator user. The PROXY_ADDRESS_FORWARDING argument is to allow direct interaction with the administrator page through a web-browser. 

You can now access the admin page of your Keycloak server by going to:
> https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/auth/admin