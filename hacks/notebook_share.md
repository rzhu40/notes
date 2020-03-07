https://stackoverflow.com/questions/39155953/exposing-python-jupyter-on-lan

https://jupyter-notebook.readthedocs.io/en/latest/public_server.html

**Need to be in the same LAN for this to work**

in remote terminal:

```bash
# get ip address
ifconfig
# generate notebook config
jupyter notebook --generate-config
# password
jupyter notebook password
```

Change some stuff in remote notebook config:

```python
c.NotebookApp.ip = '0.0.0.0' # listen on all IPs
c.NotebookApp.token = ''     # disable authentication
c.NotebookApp.allow_origin = '*' # allow access from anywhere
c.NotebookApp.disable_check_xsrf = True # allow cross-site requests
# c.GatewayClient.url = http://my-gateway-server:8888 # use gateway config for easier access
c.NotebookApp.notebook_dir = '/the/path/to/home/folder/' #starting directory
```

Don't forget the slash in front of the notebook directory, one example would be:

```python
c.NotebookApp.notebook_dir = '/Users/rzhu/Documents' #starting directory
```



run notebook in remote:

```bash
jupyter notebook --ip <remote ip address> --port <port>
```

In local browser: 

*remote IP address:port*

make life easier: generate bash scripts to open jupyter by one click:

Create a ==.sh== file, change it to executable by:

```bash
chmod +x <filename>
```

And run it by 

```bash
./<filename>
```



