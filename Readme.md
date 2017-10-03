# GIS Jupyter Notebooks

This repository builds a container image that includes the Jupyter Data
Science notebook platform.  It also installs GDAL, GEOS, and their Python bindings.  Theano and Tensorflow are also installed.

The container image is based on the
[jupyter/datascience-notebook:cf6258237ff9](https://github.com/jupyter/docker-stacks/tree/master/datascience-notebook)
image from 8/28/2017.  This image is based on the Ubuntu 16.04 (xenial)
distribution.

In addition, the [Theano](http://deeplearning.net/software/theano/)
and [Tensorflow](https://www.tensorflow.org/) Deep Learning libraries have been installed.

GDAL and GEOS libraries are installed along with the Python support for them.  Geopandas,
projections and Shapely are all installed as well.

### Building

```bash
docker build -t gis-notebooks .
```

### Running from Linux

```bash
docker run -it --rm -p 8888:8888 -v $(pwd):/home/jovyan/local brillozon/gis-notebooks
```

The default user for the container is `jovyan`.  The datascience notebook
parent includes features that can be used at run time with this container
as well.  For example, granting `sudo` access to the user.

#### Granting the user `sudo` access

The base notebook container image includes the ability to grant `sudo`
access to the user.  This can also be done when invoking this container.
This is done by setting the environment variable `GRANT_SUDO=yes` and
running the container with `--user root`.  Note that while the container
is executing as `root`, the notebook kernels are executing as the
`jovyan` user.

### Notebooks

Notebooks will be added as time permits.
