How to transfer data in and out of AiMOS?
=========================================

**IMPORTANT**: You MUST initiate the copy operation from your desktop/laptop.

You use **scp** command on your desktop/laptop to copy the data from or to the landing pad node.  Since the same gpfs file system is mounted on the landing pad nodes, front end nodes and compute nodes, the data will be available and accessible on all the nodes. For example:

* Copy some jupyter notebooks from a Linux system to the landing pad node blp01.ccni.edu. 

.. code:: bash

  $ scp multigpu_basic*.ipynb your-id@blp01.ccni.rpi.edu:~/scratch-shared/jupyter-notebooks
  PIC+Token:
  Password:
  multigpu_basic.ipynb                                                                   100% 6330    79.3KB/s   00:00
  multigpu_basics.ipynb                                                                  100% 4258    55.0KB/s   00:00

* Copy in.lj from the landing pad node blp01.ccni.rpi.edu to a directory on a Windows system. 

From a Command Prompt Terminal

.. code:: bash

  C:\D-disk\HPC>scp BMHRkmkh@blp01.ccni.rpi.edu:~/scratch-shared/in.lj .
  PIC+Token:
  Password:
  in.lj                                                                                 100%  344     4.1KB/s   00:00

