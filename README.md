# jupyterWidget-errorStackBug
Self-contained juypter notebook, demonstrating "stack_error" ipywidgets error

The only prerequsite for running this notebook, other than jupyter, notebook, and ipywidgets, is the cytoscape.js library, which is provided here.   My usual approach is to start a simple webserver hosting that library:
<pre>
python -m http.server 8099
</pre>

This short notebook was a learning exercise, and early, small and not entirely elegant python DOMWidget and javascript DOMWidgetView.

The problem reproduced first appeared in a refactored and larger self-contained notebook derived from this one. I know this often turns out to not be the case, to the embarrassment of the bug filer, but as best I can tell I had made no code changes or intentional infrastructre updates prior to the failure shown here (8 dec 2016).  I have been working on the longer version for many days and had just begun to convert the single-page ipynb into a proper cookiecutter nbexteansion.  The smaller notebook included here <b>errorStackBug.ipynb</b> shows the same error that the larger notebook does:  


<pre>
Widget backend and frontend versions are compatible extension.js:14499:26
Error: Could not create a view for model id b65af72f522449bf9566a416fd3f7147
Stack trace:
WrappedError@http://localhost:9998/nbextensions/jupyter-js-widgets/extension.js:14708:22
promiseRejection@http://localhost:9998/nbextensions/jupyter-js-widgets/extension.js:14811:30
  extension.js:14813:14
Error: Could not create view
Stack trace:
WrappedError@http://localhost:9998/nbextensions/jupyter-js-widgets/extension.js:14708:22
promiseRejection@http://localhost:9998/nbextensions/jupyter-js-widgets/extension.js:14811:30
  extension.js:14813:14
Error: Could not display model
Stack trace:
WrappedError@http://localhost:9998/nbextensions/jupyter-js-widgets/extension.js:14708:22
promiseRejection@http://localhost:9998/nbextensions/jupyter-js-widgets/extension.js:14811:30
</pre>

Some version information (which may be part of the problem):

<pre>
pip list | egrep 'notebook|widgets'
ipywidgets (6.0.0b5, /Users/paul/github/ipywidgets)
jupyterlab-widgets (0.6.3, /Users/paul/github/ipywidgets/jupyterlab_widgets)
notebook (5.0.0.dev0, /Users/paul/github/notebook)
widgetsnbextension (2.0.0b7, /Users/paul/github/ipywidgets/widgetsnbextension)
</pre>

and python modules, discovered at runtime:

<pre>
IPython 4.1.2
IPython.core.release 4.1.2
_ctypes 1.1.0
_curses b'2.2'
argparse 1.1
cgi 2.6
ctypes 1.1.0
ctypes.macholib 1.0
decorator 4.0.9
distutils 3.5.2
ipaddress 1.0
ipykernel 4.5.1
ipykernel._version 4.5.1
ipython_genutils 0.1.0
ipython_genutils._version 0.1.0
ipywidgets 6.0.0.beta5
ipywidgets._version 6.0.0.beta5
json 2.0.9
jupyter_client 4.2.2
jupyter_client._version 4.2.2
jupyter_core 4.3.0.dev
jupyter_core.version 4.3.0.dev
logging 0.5.1.2
optparse 1.5.3
parser 0.5
path 0.0.0
pexpect 4.0.1
pickleshare 0.5
pkg_resources._vendor.packaging.__about__ 16.5
pkg_resources._vendor.six 1.10.0
pkg_resources.extern.packaging 16.5
pkg_resources.extern.pyparsing 2.0.6
pkg_resources.extern.six 1.10.0
platform 1.0.7
ptyprocess 0.5
re 2.2.1
requests 2.10.0
requests.packages.chardet 2.3.0
requests.packages.urllib3 1.15.1
requests.packages.urllib3.packages.six 1.2.0
requests.utils 2.10.0
six 1.10.0
traitlets 4.3.1
traitlets._version 4.3.1
urllib.request 3.5
zlib 1.0
zmq 15.2.0
zmq.sugar 15.2.0
zmq.sugar.version 15.2.0
</pre>
