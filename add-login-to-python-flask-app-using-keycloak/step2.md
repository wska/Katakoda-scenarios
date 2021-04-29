# Create a folder to work with

Navigate to the project folder:

```
cd project
```{{execute}}

# Create a Python file to work with

Next, create a Python file using the following command:

```
> api.py
```{{execute}}

# Setting up a very basic program

You can now open the `api.py` file in the Katakoda text editor. Navigate to `project/api.py` and include the following code for the Flask application:

<pre class="file" data-filename="project/api.py" data-target="replace">
# Imports
from flask import Flask, g
from flask_oidc import OpenIDConnect
import json

# Flask settings

# Main
def main():
    pass

if __name__ == "__main__":
    main()

</pre>
