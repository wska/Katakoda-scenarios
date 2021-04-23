# Adding Flask settings

You can now open the `api.py` file in the *Katakoda* text editor. Navigate to `project/api.py`.


<pre class="file" data-filename="project/api.py" data-target="insert" data-marker="# Flask settings">
# Flask settings
app = flask.Flask(__name__)
app.config["DEBUG"] = True

# Flask API Endpoint
@app.route('/', methods=['GET'])
def home():
    return True
</pre>

Now, replace the existing pass in inside of the main function with an app.run(), signaling Flask to start and run the application. 

<pre class="file" data-filename="project/api.py" data-target="insert" data-marker="def main():
    pass">
def main():
    app.run()
</pre>

