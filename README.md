
# Flask

## setup env

```bash
pip install virtualenv
```

```bash
virtualenv env
```
## when error come 
window powershell (admin)

```bash
Set-ExecutionPolicy unrestricted
```
## or
```bash
python -m venv env

```
## Activating Virtual Environment
```bash
./env/scripts/activate.ps1
```
## Flask installation
```bash
pip install flask
```
Make
```bash
app.py
```
Run
```bash
python app.py
```
Copy in app.py
```bash
from flask import Flask
app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello, World!'
    
if __name__ == '__main__':
    app.run(debug=True , port = 8000)


```
## Make Folder
```bash
static
templates
```
Add index.html
```bash
from flask import Flask, render_template

@app.route('/')
def hello_world():
    return render_template('index.html')

```
# creat datebase
installation 
```bash
pip install flask-sqlalchemy
```
import
```bash
from flask_sqlalchemy import SQLAlchemy
```
go this
```bash
https://flask-sqlalchemy.palletsprojects.com/en/2.x/config/
```
initialize
```bash
app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///todo.db'
app.config['SQLALCHEMY_TRACK_MODIFICATIONS'] = False
db = SQLAlchemy(app)
app.app_context().push()
```
```bash
class Todo(db.Model):
    sno = db.Column(db.Integer, primary_key = True)
    Title = db.Column(db.String(200), nullable=False)
    desc = db.Column(db.String(200), nullable=False)
    date_cr = db.Column(db.DateTime, default=datetime.utcnow)

    def __repr__(self) ->str:
        return f"{self.sno} - {self.Title}"
```
open python in shell
```bash
python
```
create the initial database
```bash
from yourapplication import db
db.create_all()
```
