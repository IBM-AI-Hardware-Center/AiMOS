.. _hints_and_tips:

Hints and Tips
==============

General:
^^^^^^^^
#. You must be in the front end node to set up your system environment.
#. You must be in the front end node to install conda or create a new conda environment.

DCS Cluster (Power):
^^^^^^^^^^^^^^^^^^^^
#. If you want to use the  Powers System cluster, i.e. DCS Cluster, log in to the dcsfen01.ccni.rpi.edu node or dcsfen02.ccni.rpi.edu node.
#. Note that spectrum_mpi is installed in the DCS Cluster. You can use **module spider** to find all possible modules and extensions.


NPL Cluster (X86):
^^^^^^^^^^^^^^^^^^

#. If you want to use the  x86 cluster, i.e. NPL Cluster, log in to the nplfen01.ccni.rpi.edu node.
#. For the NPL cluster, avoid using system memory together with GPU memory since the data transfer is using the PCI bus. It is not the high speed connection.
#. Note that openmpi is installed in the NPL Cluster.  You can use **module spider** to find all possible modules and extensions.
