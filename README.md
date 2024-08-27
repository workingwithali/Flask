
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
Copy in app.py
```bash
  from flask import Flask
app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello, World!'
    
if __name__ = '__main__' :
  app.run(degbug=Trun)

```