# jupyter-jsc-custom-share-template
Template repository for custom JupyterHub templates and static files.

To use this template, click **Use this template** above the file list and select **Include all branches** when creating your repository.

Reference templates and static files used by the Jupyter-JSC JupyterHub can be found [in this repository](https://github.com/FZJ-JSC/jupyter-jsc-share).
## Static

This branch contains any static files that should be changed on the production JupyterHub instance.

Custom css may be places in the `css` directory. The css file name usually corresponds to the template file name, e.g. `header.html -> header.css`, although you may change this in the template file.

Any custom images or logos should be placed in the correct subdirectory under the `images` directory.