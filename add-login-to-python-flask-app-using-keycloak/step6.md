# Setting up Keycloak 

# Creating the Keycloak user 

Next, we will create a user. To your left, you can see two "Submenus". Click on the "User" on the lower one. This puts you on the `Lookup` tab. On the corner to your right you will se the button **add user**. Go ahead and click it.

<img src="https://github.com/wska/katacoda-scenarios/blob/main/add-login-to-python-flask-app-using-keycloak/img/3.png?raw=true" width="500">

Enter a name for the user and make sure that `Email Verified` is activated, else the user will be flagged as "incomplete" later on. This allows for using email verification(a very common feature in modern applications) if one wants it, but it is not part of this tutorial.  

<img src="https://github.com/wska/katacoda-scenarios/blob/main/add-login-to-python-flask-app-using-keycloak/img/4.png?raw=true" width="500">

Now, navigate to `Credentials` on the the user management page and set a password of your choice. Just remember what you set it to. Obviously. Make sure you toggle the **Temporary** setting to off, or you will be prompted to update your password upon the next login. 

<img src="https://github.com/wska/katacoda-scenarios/blob/main/add-login-to-python-flask-app-using-keycloak/img/5.png?raw=true" width="500">
