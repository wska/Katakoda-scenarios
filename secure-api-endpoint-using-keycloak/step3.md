# Adding Flask settings

Let us now add a Flask API endpoint. It is typical to set up some basic configuration along with an initialization of the Flask application. Let us also add a very simple open endpoint, which simply returns a greeting:

<pre class="file" data-filename="project/api.py" data-target="insert" data-marker="# Flask settings">
# Flask settings
app = Flask(__name__)

# Flask Open Endpoint
@app.route('/', methods=['GET'])
def home():
    return "Hello from the open endpoint\n"

# Flask Secure Endpoint

# Flask Login Redirect
</pre>

We also added markers for additional endpoints, which have very [*spoilery*](https://media.makeameme.org/created/spoilers-spoilers-everywhere-5cd1c4.jpg) names. More on these later.

This setups up some basic Flask configuration and creates an API endpoint, located at the root of our hostaddress ("/").

Now, replace the existing pass inside of the main function with an `app.run()`, signaling Flask to start and run the application:

<pre class="file" data-filename="project/api.py" data-target="insert" data-marker="def main():
    pass">
def main():
    app.run(host='0.0.0.0', port=5000, debug=True)
</pre>

# Access the URL

You can start the application by running:
```python3 api.py```{{execute}}

One can now query the API (i.e. using `curl`). Either open up a new terminal window, since `Terminal 1` is used for the Flask application, or use the clickable function on the command below:

```curl http://127.0.0.1:5000/```{{execute T2}}
