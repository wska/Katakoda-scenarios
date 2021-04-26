# Starting up Keycloak

Since we pulled the Docker image earlier during Step 1, we can now launch the Keycloak server using docker. Using the new Terminal 2 window, we can run:


```
docker run -p 8080:8080 -e PROXY_ADDRESS_FORWARDING=true -e KEYCLOAK_USER=admin -e KEYCLOAK_PASSWORD=admin quay.io/keycloak/keycloak:12.0.4
```{{execute T2}}

 This starts the Keycloak docker image and insert a basic administrator user. This typically takes a little while to start up. You should finally see that the "Admin console is listening....". The PROXY_ADDRESS_FORWARDING argument is to allow direct interaction with the administrator page through a web-browser. 

You can now access the admin page of your Keycloak server by opening the following URL:
> https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/auth/admin
and log in using the specified credentials in the initial startup of the image:

> Username: admin

> Password: admin 
