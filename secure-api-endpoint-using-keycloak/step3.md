# Adding Flask settings

You can now open the `api.py` file in the *Katakoda* text editor. Navigate to `project/api.py`.


<pre class="file" data-filename="project/api.py" data-target="insert" data-marker="# Flask settings">

app = flask.Flask(__name__)
app.config["DEBUG"] = True


@app.route('/', methods=['GET'])
def home():
    return "<h1>Hello</h1><p>Test</p>"

</pre>

