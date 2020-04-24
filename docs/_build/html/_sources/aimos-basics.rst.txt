.. _what-is-aimos:

What is AiMOS?
==============

AiMOS (short for \ **A**\rtificial \ **I**\ntelligence \ **M**\ultiprocessing \ **O**\ptimized \ **S**\ystem) serves as the test bed for 
the IBM Research AI Hardware Center. AiMOS consists of two(2) front end nodes and two hundred and fifty two(252) AC922 compute nodes configured in a fourteen(14) rack system.

Each compute node has: 

* 2 x 20-core POWER9 processors (Summit’s variant)
* 6 x NVIDIA Volta V100 GPUs with 32 GB of HBM each
* 512 GB of DRAM
* 1.6 TB NVMe SSD storage
* Dual, 100 Gb/sec Mellanox IB links

For more information see https://secure.cci.rpi.edu/wiki/index.php?title=DCS_Supercomputer

There are the landing pad nodes and the front end nodes in addition to the compute nodes in AiMOS. `Slurm <https://slurm.schedmd.com/overview.html>`_ is used for resource management and job scheduler.

What are the landing pad nodes?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Landing pad nodes are nodes that have an external IP for you to log in. You will need to log in to one of the landing pad nodes before you can access the AiMOS systems.

There are 4 landing pad nodes for AiMOS:

* blp01.ccni.rpi.edu
* blp02.ccni.rpi.edu
* blp03.ccni.rpi.edu
* blp04.ccni.rpi.edu

For more information see https://secure.cci.rpi.edu/wiki/index.php?title=Landing_pad

What are the front end nodes?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The front end nodes (a.k.a. login nodes) are nodes where you find Slurm, compilers, libraries, headers, development tools, etc. This is where you build your executables if needed, issue Slurm commands to submit jobs. In order to see some of the executables, libraries, etc., you may need to use module to load them first. For how to, please see section How to load different modules for your development and testing? section later in this documentation.

There are two front end nodes in AiMOS.

* dcsfen01.ccni.rpi.edu
* dcsfen02.ccni.rpi.edu

What are the compute nodes?
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Compute nodes are nodes where you execute your application.  There are 252 compute nodes in AiMOS.  They are AC922 with 6 GPU each. You can only log in to the compute nodes that are allocated to you via Slurm commands.

* dcs001 - dcs216
* dcs235 - dcs270

