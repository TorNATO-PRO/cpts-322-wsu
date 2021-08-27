# Lecture 3 Software Engineering Principles

## Encoding Data
- XML, JSON, YAML, TOML

Basic Flask App Architecture

- Browser (HTTP Client Side)

- Flask Web Server (HTTP Server Side)

### Simple Flask Hello-World Application

```python
# creates Flask app
from flask import Flask
app = Flask(__name__)

@app.route('/')
def index():
    return "<h1>Hello!</h1>"

@app.route('/course')
def course():
	return '<h1>Hello class!</h1>'

# this is an arbitrary name that is received as a route
@app.route('/course/<string:name>')
def mycourse(name):
	return '<h1>Hello, {0} class!</h1>'.format(name)

@app.route('/appname')
def appname():
    return "<h1>Application name:{}</h1>".format(__name__)

# starts the flask server in debug mode
if __name__ == '__main__':
    app.run(debug=True)
```

To run, you simply save this as `hello.py` and then go `python hello.py`.

## Flask Templates

- Why?
  - Separate logic from presentation
- How?
  - Create HTML templates (02_FlaskForms)
  - Create links between pages (03_FlaskForms_linkpages)

### Code example

Directory Stucture:

- templates/
  - course.html
  - index.html
- app.py
- README.md

**course.html**
```html
<h1>Hello, {{name}} class!</h1>
```

**index.html**
```html
<h1>Hello!</h1>
<p>Please choose your class: </p>
<ul>
    <li><a href="#"> CptS 322 </a></li>
    <li><a href="#"> CptS 355</a></li>
    <li><a href="#"> CptS 321</a></li>
    <li><a href="#"> CptS 451</a></li>
</ul>
```

**app.py**
```python
from flask import Flask, render_template
app = Flask(__name__)

@app.route('/')
def index():
    return render_template('index.html')

@app.route('/course/<name>')
def course(name):
    return render_template('course.html', name=name)

if __name__ == '__main__':
    app.run(debug=True)
```

