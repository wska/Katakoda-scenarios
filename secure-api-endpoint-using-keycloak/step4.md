# Starting up Keycloak

Since we pulled the Docker image earlier during Step 1, we can now launch the Keycloak server using docker. Open a new terminal windows and input:



> https://[[HOST_SUBDOMAIN]]-80-[[KATACODA_HOST]].environments.katacoda.com

> docker run -p 80:80 -e KEYCLOAK_USER=admin -e KEYCLOAK_PASSWORD=admin quay.io/keycloak/keycloak:12.0.4