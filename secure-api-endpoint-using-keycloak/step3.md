# Adding Flask settings

You can now open the `api.py` file in the *Katakoda* text editor. Navigate to `project/api.py`. And write some code for the Flask app:


<pre class="file" data-filename="project/api.py" data-target="insert" data-marker="# Flask settings">
# Flask settings
app = flask.Flask(__name__)
app.config["DEBUG"] = True

# Flask Open Endpoint
@app.route('/', methods=['GET'])
def home():
    return "Hello from /"


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

One can now query the API, for example using curl:
```curl http://127.0.0.1:5000/```{{execute}}
