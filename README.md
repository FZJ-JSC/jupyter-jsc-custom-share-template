# jupyter-jsc-custom-share-template
Template repository for custom JupyterHub templates and static files.

To use this template, click **Use this template** above the file list and select **Include all branches** when creating your repository.

Reference templates and static files used by the Jupyter-JSC JupyterHub can be found [in this repository](https://github.com/FZJ-JSC/jupyter-jsc-share).

## Templates

[Official JupyterHub documentation](https://jupyterhub.readthedocs.io/en/stable/reference/templates.html)

* Change header and footer as desired. Any logos should be placed in the `static` branch. 

* You may want to update the meta data in `page.html`.

* You may want to change the login text in `<div id="upper-login-div">` and carousel texts via the `carousel_item` Jinja macros in `login.html`.

* If you want to link to different or additional pages, update `links.html` (`link_list` Jinja macro) and `sidebar.html` (`ul` Jinja macro).

* The privacy policy may be updated in `dps.html`.

## Available variables

Some variables are passed from JupyterHub and available as Jinja variables in the templates. The following variables are available in all templates:

```python
base_url  # hub.base_url
prefix  # base_url
user  
login_url
login_service
logout_url
static_url  # url location of static files
version_hash  # e.g. datetime.now().strftime("%Y%m%d%H%M%S")
services  # list of services returned by `get_accessible_services(user)`
parsed_scopes  # scopes for a user
expanded_scopes  

# and any variables defined in under `template_vars` in the JupyterHub config file
```

## Why won't my template render correctly?
Jupyter-JSC uses a custom JupyterHub installation which passes some variables your local installation is unlikely to have. This should affect only the templates `home.html`, `spawn_pending.html` and `footer.html`.

The custom JupyterHub variables include `incident_messages`, `custom_config`, `maintenance_list`, `spawner_options_form` and `additional_spawn_options`. 

You can try to get around this by initializing these variables directly via Jinja in some templates, although this might not work in all cases. For example in `footer.html`:

```jinja
{% set incident_messages = {} %}
```