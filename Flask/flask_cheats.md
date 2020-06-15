### Welcome to Flask Cheats
```Python
# !pip install Flask
from flask import (
                    Flask, 
                    jsonify, 
                    url_for,
                    render_template,
                    request,
                    redirect,
                    abort,
                    session
                    )

app = Flask(__name__)

@app.route('/', methods = ['GET'])
def home():
  return jsonify({'test':'Hello World'})

if __name__=='__main__':
  app.run(debug=True, port=5000)
```
|Converter Type|Converter explanation|
|------|------------------------------------------|
|string|(default) accepts any text without a slash|
|int|accepts positive integers|
|float|accepts positive floating point values|
|path|like string but also accepts slashes|
|uuid|accepts UUID strings|

#### Parameters which we can use for request
* request.args.get('something')
* request.files.get('somefile')
* request.method == 'POST'
* request.path == '/home'
* request.form.get('formdata',None)
* request.cookies.get('username')
* request.get_json()

#### Lets create a simple API using flask
```Python
from flask import Flask, request,jsonify

app = Flask(__name__)

@app.route('/<string:name>',methods = ['GET'])
def home(name):
  return jsonify({'name':name})

app.run(debug=True)
```