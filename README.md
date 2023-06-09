## Dockerfile Update

We made an update to the Dockerfile to include the installation of Elyra. 

In the Dockerfile, the Python package installation is managed by the `RUN pip install` command. To this command, we've added `--upgrade "elyra[all]"` which instructs pip to install and/or upgrade Elyra and all of its optional dependencies.

The updated Dockerfile command looks like this:

```Dockerfile
RUN pip install --no-cache-dir \
        shortid \
        nbgitpuller \
        --upgrade "elyra[all]" 
```

In this command:
- `pip install` is the command used to install Python packages.
- `--no-cache-dir` is an option that tells pip not to use or create a cache, which can help to reduce the Docker image size.
- `shortid` and `nbgitpuller` are Python packages that were already being installed.
- `--upgrade "elyra[all]"` is the new addition which instructs pip to install (or upgrade if it's already installed) Elyra with all optional dependencies.

Elyra is a set of AI-centric extensions to JupyterLab. It extends JupyterLab by offering a visual interface for creating comprehensive, executable descriptions of computational pipelines. This includes functionalities such as local and cloud-based Notebook execution, data preprocessing, model training and evaluation, and more.

---

