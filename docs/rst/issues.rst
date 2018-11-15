.. _known_issues-label:

Known issues
============

General
-------

#. When the server starts a **waiting page** is displayed. The **automatic
   forwarding** to the notebook occasionally fails. You have to refresh the
   page manually using your browser in this case.

#. **Servers cannot be stopped** using the web frontend

   -  Running servers on the supercomputer can be stopped by deleting
      the job with ``qdel``
   -  Local servers cannot be killed easily at the moment. (Local servers not available at the moment)

#. There is now indication about **remaining walltime** in the Jupyter
   notebook. 



Spawner
-------

#. The greeting page is generated the first time a user is visiting it. This has the following implications:
   
   - The **available credits** of the projects are **not** updated everytime the JupyterHub main page is opened
   - Newly allocated project might not show up in the list.

