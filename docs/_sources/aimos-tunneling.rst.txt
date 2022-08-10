How to display the WebGUI for a jupyter notebook running on a compute node via ssh tunnelling?
==============================================================================================

Prerequisites
^^^^^^^^^^^^^

Conda and jupyter notebook are installed on the node. For how to see :ref:`install-conda` and :ref:`install-jupyter`

Allocate a compute node
^^^^^^^^^^^^^^^^^^^^^^^

For example, allocate a compute node for 30 minutes:

::

  salloc -N 1 --salloc -N 1 --gres=gpu:6 -t 30

After the command returns, you can run squeue to find the allocated node.

.. code:: bash

  squeue
             JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON)
            172886       dcs     bash BMHRkmkh  R       0:13      1 dcs085


Start the jupyter notebook on the allocated compute node
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

You then ssh to the allocated node, activate to the appropriated conda environment, change directory to where the jupyter notebooks are in, then  starting jupyter notebook as follow:

.. code:: bash

  (wmlce-1.7.0) [your-id@dcs085 ~]$ jupyter notebook --ip=0.0.0.0 --no-browser



SSH tunnelling on a Linux or MAC OSX node
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Start the ssh session to one of the landing pad nodes and map the port 8888 from dcs085 to port 8888 on the local host.  For example:

.. code:: bash

  [id@kvt-rhel ~]$ ssh -L8888:dcs085:8888 BMHRkmkh@blp01.ccni.rpi.edu


Go to the browser on the node, enter the following to tunnel to the jupyter notebook running on the compute node to the localhost.

.. code:: bash

  http://localhost:8888


You should see the jupyter notebook after you enter the token at the login prompt.

.. figure:: jupyter-l.png


SSH tunneling via PUTTY on Windows
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Go to the putty entry for the landing pad node.  For example:

.. figure:: putty2.png

Go section Connection->SSH->Tunnels, enter the jupyter notebok URL on the compute node and click **Add**, for example:

.. figure:: putty-tunnel.png

Start the putty session and login to the landing node as usual.

After that, go to your browser and enter the following to tunnel to the jupyter notebook running on the compute node.

.. code:: bash

  http://localhost:18889


You should see the jupyter notebook after you enter the token at the login prompt.

.. figure:: jupyter-w.png

