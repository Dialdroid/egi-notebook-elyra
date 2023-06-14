### Adding Elyra Extensions and Building JupyterLab

To include the Elyra extensions and build JupyterLab within the Dockerfile, follow these steps:

1. Add the installation of Elyra extensions to the existing `RUN mamba install -y --quiet` command:

   ```Dockerfile
   RUN mamba install -y --quiet \
           cftime \
           ipympl \
           jmespath \
           psycopg2 \
           boto3 \
           folium \
           tensorflow \
           tqdm \
           lxml \
           pymongo \
           rasterstats \
           geopandas \
           ipywidgets \
           matplotlib \
           scipy \
           lightgbm \
           eo-learn \
           plotly \
           graphviz \
           jq \
           nb_conda_kernels \
           dwave-ocean-sdk==5.5.0 \
           amazon-braket-sdk==1.31.0 \
           elyra \
       && conda clean --all
       
2. The Jupyter build was added to load each Elyra extension into the JupyterLab graphical environment.

   ```Dockerfile
   RUN jupyter lab build

