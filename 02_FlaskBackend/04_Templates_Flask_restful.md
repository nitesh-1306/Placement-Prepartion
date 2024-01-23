### Flask RESTful Revision

### Basic template
```python
from flask import Flask
from flask_restful import Resource, Api

app = Flask(__name__)
api = Api(app)

class HelloWorld(Resource):
    def get(self):
        return {'message': 'Hello, World!'}

api.add_resource(HelloWorld, '/')

if __name__ == '__main__':
    app.run(debug=True)
```


### Token Based Authentication
```python
from flask import Flask
from flask_restful import Resource, Api, reqparse
from flask_httpauth import HTTPBasicAuth

app = Flask(__name__)
api = Api(app)
auth = HTTPBasicAuth()

# In-memory user data
users = {
    'john': 'secret',
    'susan': 'another_secret'
}

@auth.verify_password
def verify_password(username, password):
    if username in users and users[username] == password:
        return username

class PrivateResource(Resource):
    @auth.login_required
    def get(self):
        return {'message': 'Welcome to the private resource!'}

api.add_resource(PrivateResource, '/private')

if __name__ == '__main__':
    app.run(debug=True)
```