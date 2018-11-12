Compute kernels
===============

The standard python kernel provided by JupterHub is running python 3.6
and has very few packages installed. You can used it for some testing,
but it will most likely not cover your workflow. It is impossible for us
to cover every workflow due to different needs in software and software
version. Therefore we intend to give the users a way to install and
maintain their own software as we do it for python packages. The
procedure is based on the python package management descrived on the
`VSC
homepage <https://www.vscentrum.be/cluster-doc/development/python-packages>`__.


Conda environments in Jupyter notebook
--------------------------------------

After installing a conda environment and introducing it to JupterHub you
can choose it from the drop down menu when starting a new kernel.

We will create an own conda environment with the following software:

- ``python 2.7``
- ``numpy``
- ``scipy``
- ``mayavi``
- ``matplotlib``
- ``pandas``
- ``pandas``
- ``tensorflow``
- ``seaborn``

We assume here that your miniconda environment is installed to the following path: ``${VSC_DATA}/software/${VSC_INSTITUTE_CLUSTER}/miniconda3/envs/p27env/``

Please adapt this to the path of your software installation.

.. code:: bash

   conda create -n p27env python=2.7 numpy scipy mayavi matplotlib pandas tensorflow seaborn
   ${VSC_DATA}/software/${VSC_INSTITUTE_CLUSTER}/miniconda3/envs/p27env/bin/python -m ipykernel install  --prefix=${VSC_HOME}/.local/ --name 'p27env' 


