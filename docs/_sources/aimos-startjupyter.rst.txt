.. _start-jupyter:

How to Start Jupyter notebook?
==============================

**IMPORTANT:**

* You are logging in to one of the front end nodes. For more information see :ref:`how-to-login`

* Conda was installed and activated. For more information see :ref:`install-conda`.

* Jupyter notebook was installed. For how to  see :ref:`install-jupyter`.

Allocate a compute node
^^^^^^^^^^^^^^^^^^^^^^^

For example, allocate a compute node for 30 minutes:

.. code:: bash

  salloc -N 1 --salloc -N 1 --gres=gpu:6 -t 30

After the command returns, you can run squeue to find the allocated node.

.. code:: bash

  squeue
           JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON)
          172886       dcs     bash BMHRkmkh  R       0:13      1 dcs085

After the command returns, you can run squeue to find the allocated node.

.. code:: bash

  (base) [your-id@dcsfen01 wmlce-1.7.0]$ conda list | grep notebook
  notebook                  6.0.3                    py37_0    conda-forge

Start Jupyter Notebook on the allocated compute node
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

* SSH to the compute node

.. code:: bash

  (base) [BMHRkmkh@dcsfen01 ~]$ ssh dcs035
  Warning: Permanently added 'dcs035,172.31.236.35' (ECDSA) to the list of known hosts.

  (base) [BMHRkmkh@dcs035 ~]$
  
* Activate to the conda environment that is appropriated for your notebook.

.. code:: bash

  (base) [BMHRkmkh@dcs035 ~]$ conda activate wmlce-1.7.0
  (wmlce-1.7.0) [BMHRkmkh@dcs035 ~]$ toshare
  (wmlce-1.7.0) [BMHRkmkh@dcs035 scratch-shared]$ 

* Start Jupyter Notebook

.. code:: bash

  (wmlce-1.7.0) [BMHRkmkh@dcs035 scratch-shared]$ jupyter notebook --ip=0.0.0.0 --no-browser





