.. _what-is-aimos:

What is AiMOS?
==============

AiMOS (short for \ **A**\rtificial \ **I**\ntelligence \ **M**\ultiprocessing \ **O**\ptimized \ **S**\ystem) serves as the test bed for 
the IBM Research AI Hardware Center.  AiMOS consists of two(2) clusters:

* `DCS Cluster <https://secure.cci.rpi.edu/wiki/clusters/DCS_Supercomputer>`_ has two hundred and fifty two(252) AC922 compute nodes configured in a fourteen(14) rack system. Each compute node has:

  * 2 x 20-core POWER9 processors (Summit’s variant)
  * 6 x NVIDIA Volta V100 GPUs with 32 GB of HBM each
  * 512 GB of DRAM
  * 1.6 TB NVMe SSD storage
  * Dual, 100 Gb/sec Mellanox IB links


* `NPL Cluster <https://secure.cci.rpi.edu/wiki/clusters/NPL_Cluster>`_ contains 40 nodes, each with:

  * 2x 20 core 2.5 GHz Intel Xeon Gold 6248
  * 8x NVIDIA Tesla V100 GPU each with 32 GiB HBM
  * 768 GiB RAM per node
  * Dual 100 Gb EDR Infiniband

There are the landing pad nodes and the front end nodes in addition to the compute nodes in AiMOS. `Slurm <https://slurm.schedmd.com/overview.html>`_ is used for resource management and job scheduler.

What are the landing pad nodes?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Landing pad nodes are nodes that have an external IP for you to log in. You will need to log in to one of the landing pad nodes before you can access the AiMOS systems.

There are 4 landing pad nodes for AiMOS:

* blp01.ccni.rpi.edu
* blp02.ccni.rpi.edu
* blp03.ccni.rpi.edu
* blp04.ccni.rpi.edu

For more information see https://secure.cci.rpi.edu/wiki/landingpads

What are the front end nodes?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The front end nodes (a.k.a. login nodes) are nodes where you find Slurm, compilers, libraries, headers, development tools, etc. This is where you build your executables if needed, issue Slurm commands to submit jobs. In order to see some of the executables, libraries, etc., you may need to use module to load them first. For how to, please see :ref:`load-module` section later in this documentation.

There are two front end nodes for DCS Cluster: 

* dcsfen01.ccni.rpi.edu
* dcsfen02.ccni.rpi.edu

There is one front end node for NPL Cluster:

* nplfen01.ccni.rpi.edu

For more information see https://secure.cci.rpi.edu/wiki/clusters/

What are the compute nodes?
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Compute nodes are nodes where you execute your application.  There are 252 compute nodes in DCS Cluster and 40 compute nodes in NPL Cluster in AiMOS. You can only log in to the compute nodes that are allocated to you via Slurm commands.

