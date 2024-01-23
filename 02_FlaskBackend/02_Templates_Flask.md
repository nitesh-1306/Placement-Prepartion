# Flask Backend Revision


### Basic Template
```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello, World!'

if __name__ == '__main__':
    app.run(debug=True)
```

### Routing in Flask
```python
@app.route('/')
def home():
    return 'Home Page'

@app.route('/about')
def about():
    return 'About Page'
```
### Rendering Templates

#### Project Directories
```md
project-root/
│
├── app/
│   ├── static/
│   │   ├── css/
│   │   │   └── style.css
│   │   ├── js/
│   │   └── img/
│   │
│   ├── templates/
│   │   ├── layout.html
│   │   ├── home.html
│   │   ├── about.html
│   │   └── partials/
│   │       ├── header.html
│   │       └── footer.html
│   │
│   ├── __init__.py
│   ├── routes.py
│   ├── models.py
│   └── forms.py
│
├── instance/
│   └── config.py
│
├── tests/
│
├── venv/
│
├── config.py
├── requirements.txt
└── run.py
```

```python
from flask import render_template

app = Flask(__name__, static_folder='static', template_folder='templates')

@app.route('/profile/<username>')
def profile(username):
    return render_template('profile.html', username=username)
```

#### Linking of static files inside templates
```html
<link rel="stylesheet" href="{{ url_for('static', filename='css/style.css') }}" />
```
### Form Handling
```python
from flask import Flask, render_template, request

@app.route('/login', methods=['GET', 'POST'])
def login():
    if request.method == 'POST':
        username = request.form['username']
        password = request.form['password']
        # Validate and process the form data
    return render_template('login.html')
```