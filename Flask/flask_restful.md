#### Lets look at the flask restful package
for installation use the pip install

    $ pip install Flask-RESTful
            OR
    $ pip install flask-restful

```Python
# Sample flask api with restful
from flask import Flask
from flask_restful import Resource, Api

app = Flask(__name__)
api = Api(app)

class LetsTestREST(Resource):

    def get(self):
        return {'hello' : 'world'}

api.add_resource(LetsTestREST, '/')

app.run(debug=True)
```
#### As of now we have seen requests without parameters in URL, now lets see how to incorporate them in restful
```Python
class TestingParameter(Resource):
    def get(self,name):
        return {'input_parameter': name}

api.add_resource(TestingParameter, '/test/<string:name>')
```