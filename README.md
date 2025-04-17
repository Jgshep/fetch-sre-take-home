# fetch-sre-take-home
My take on fetch's take-home SRE challenge. Will be made private (or removed) once processed.

# Installation

main.py requires PyYAML, so we need a virtual environment. I'm on a fresh debian installation, so I didn't have this installed yet.

```
sudo apt-get install python3.12-venv
```
Make a venv outside of the repository:
```
mkdir ~/fetch
python3 -m venv ~/fetch/app
```

From this point on, we'll be using the pip and python binaries located in the venv.

Install requirements - PyYAML and requests. These have some dependencies of their own that will also install.
```
~/fetch/app/bin/pip install -r requirements.txt
```

Once these are installed, you can run the program with the following (assuming the venv was created as described, and you're in the repository root. Replace paths as needed.):
```
/fetch/app/bin/python3 main.py sample.yaml
```

## Changes I made

In the `check_health` function, I added the missing functionality to account for an undefined method (line 17 - 20). 

In the `requests.request` (line 22), I changed `JSON=body` to `data=body`. The `body` variable is a dict object, not json, which results in a compilation error. 

I also added the `timeout` to the `requests.request` (line 22) and added a ConnectTimeout exception (line 29 - 30).


