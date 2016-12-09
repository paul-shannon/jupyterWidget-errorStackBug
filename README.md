# jupyterWidget-errorStackBug
Self-contained juypter notebook, demonstrating "stack_error" ipywidgets error

This short notebook was a learning exercise.  The problem reproduced first appeared in a refactored and larger self-contained notebook. I know this often turns out to not be the case, to the embarrassment of the bug filer, but as best I can tell, there were no code changes or intentional infrastructre updates prior to the failure shown here (8 dec 2016).  This smaller notebook also shows the same error:

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
