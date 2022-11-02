# jupyter-jsc-custom-share-template
Template repository for custom JupyterHub templates and static files.

To use this template, click **Use this template** above the file list and select **Include all branches** when creating your repository.

Reference templates and static files used by the Jupyter-JSC JupyterHub can be found [in this repository](https://github.com/FZJ-JSC/jupyter-jsc-share).

## How to create custom files

You have the options to only modify files which should be different from the [default files](https://github.com/FZJ-JSC/jupyter-jsc-share/tree/main/jupyterhub) used by Jupyter-JSC. 

To help you to know which files you should modify, the `templates` branch contains files which frequently need to be modified for custom JupyterHub instances. The `static` branch contains frequently modified static files such as css files, custom logos, etc.

If you don't want to modify a certain file but use the Jupyter-JSC default, delete it from the respective branch to take advantage of any updates such as bugfixes on Jupyter-JSC's side.

If you want to modify a file which is not present in this template repository, feel free to copy it from [the Jupyter-JSC repository](https://github.com/FZJ-JSC/jupyter-jsc-share) or create your own from scratch.


## How to test custom files
You can and should test any changes. In your [JupyterHub config file](https://jupyterhub.readthedocs.io/en/stable/getting-started/config-basics.html), you can specify template and data paths:
```python
# jupyterhub_config.py

c.JupyterHub.template_paths = ["path/to/template/files"]  # list
c.JupyterHub.data_files_path = "path/to/static/files"  # string
```

Then, start a local JupyterHub using the config file: `jupyterhub -f /path/to/jupyterhub_config.py`