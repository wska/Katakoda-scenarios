# Adding Flask settings
Let us now add a Flask api endpoint. It is typical to set up some basic configuration along with an initialization of the flask app.



<pre class="file" data-filename="project/api.py" data-target="insert" data-marker="# Flask settings">
# Flask settings
app = flask.Flask(__name__)
app.config["DEBUG"] = True

# Flask Open Endpoint
@app.route('/', methods=['GET'])
def home():
    return "Hello from the open endpoint\n"


# Flask Secure Endpoint
# ... spoiler free


# Flask Secure API Endpoint
# ... spoiler free
</pre>



This setups up some basic flask configuration and creates an API endpoint, located at the root of our hostaddress ("/").
Now, replace the existing pass in inside of the main function with an app.run(), signaling Flask to start and run the application. 

<pre class="file" data-filename="project/api.py" data-target="insert" data-marker="def main():
    pass">
def main():
    app.run()
</pre>

# Access the URL
If you now start the application by running:
```python3 api.py```{{execute}}

One can now query the API (using something like curl). Either open up a new terminal window (since the current one is used to tbe Flask app) or click below:
```curl http://127.0.0.1:5000/```{{execute T2}}
