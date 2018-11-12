User-defined compute kernels
============================

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

You can create several conda environment and make all of them available to JupyterHub.

**Note**: We are looking forward to hear user feedback if everything works as expected. It is especially interesting to hear if there are any side effects with the Python JupyterHub is running on.

Environment creation
^^^^^^^^^^^^^^^^^^^^

We assume that miniconda has been installed to ``${VSC_DATA}/software/${VSC_INSTITUTE_CLUSTER}/miniconda3``. If you have installed it to a different path you have to adapt the following commands accordingly.

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

**Note**: Instead of creating a new environment you can also introduced an existing environment to your JupyterHub. In this case you can skip the creation of the environment.

We assume here that your miniconda environment is installed to the following path: 

.. code-block:: bash

   ${VSC_DATA}/software/${VSC_INSTITUTE_CLUSTER}/miniconda3/envs/p27env/

Please adapt this to the path of your software installation.

1. Create a new conda environment named ``p27env``

   .. code-block:: bash

      conda create -n p27env python=2.7 numpy scipy mayavi matplotlib pandas tensorflow seaborn

2. Install environment to ``${VSC_HOME}/.local`` so JupyterHub can find it.
  
   .. code-block:: bash

      ${VSC_DATA}/software/${VSC_INSTITUTE_CLUSTER}/miniconda3/envs/p27env/bin/python -m ipykernel install  --prefix=${VSC_HOME}/.local/ --name 'p27env'

3. Connect to JupyerHub and verify that the new environment appears. It should look like in the following:

   .. figure:: images/choose_kernel.png
      :width: 400px
      :scale: 70%
      :alt: Context menu showing available compute kernels
      :align: center

4. Test the environment and make sure that it works as intended.

