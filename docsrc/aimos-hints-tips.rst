.. _hints_and_tips:

Hints and Tips
==============

General
^^^^^^^
#. You must be in the front end node to set up your system environment.
#. You must be in the front end node to install conda or create a new conda environment.

DCS Cluster (Power)
^^^^^^^^^^^^^^^^^^^
#. If you want to use the  Powers System cluster, i.e. DCS Cluster, log in to the dcsfen01.ccni.rpi.edu node or dcsfen02.ccni.rpi.edu node.
#. Note that spectrum_mpi is installed in the DCS Cluster. You can use **module spider** to find all possible modules and extensions.


NPL Cluster (X86)
^^^^^^^^^^^^^^^^^^

#. If you want to use the  X86 cluster, i.e. NPL Cluster, log in to the nplfen01.ccni.rpi.edu node.
#. For the NPL cluster, avoid using system memory together with GPU memory since the data transfer is using the PCI bus. It is not the high speed connection.
#. Note that openmpi is installed in the NPL Cluster.  You can use **module spider** to find all possible modules and extensions.


Transfer data in and out of AiMOS
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

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

For transferring a large file see  https://docs.cci.rpi.edu/landingpads/Transferring_Large_Files/


.. _conda-init-bashrc:

Conda Init in .bashrc
^^^^^^^^^^^^^^^^^^^^^

This snippet of .bashrc bases on the hardware architecture of the node and execute the applicable conda init code.  It also assumes that the anaconda is installed in ~/scratch/miniconda3 for Power environment (i.e. DCS cluster) and in ~/scratch/miniconda3-x86 for X86 environment (i.e. NPL cluster).  Please modify the project name BMHR to your project, BMHRkmkh  to your user ID, and the PATH of your conda root.

.. code:: bash

   arch=`uname -m`
   if [[ $arch == "ppc64le" ]]
   then
           # >>> conda initialize >>>
           # !! Contents within this block are managed by 'conda init' !!
           __conda_setup="$('/gpfs/u/home/BMHR/BMHRkmkh/scratch/miniconda3/bin/conda' 'shell.bash' 'hook' 2> /dev/null)"
           if [ $? -eq 0 ]; then
               eval "$__conda_setup"
           else
               if [ -f "/gpfs/u/home/BMHR/BMHRkmkh/scratch/miniconda3/etc/profile.d/conda.sh" ]; then
                   . "/gpfs/u/home/BMHR/BMHRkmkh/scratch/miniconda3/etc/profile.d/conda.sh"
               else
                   export PATH="/gpfs/u/home/BMHR/BMHRkmkh/scratch/miniconda3/bin:$PATH"
               fi
           fi
           unset __conda_setup
           # <<< conda initialize <<<

   else
           host_name=`hostname -s | cut -c 1-3`
           if [[ $host_name != "blp" ]]
           then
             # >>> conda initialize >>>
             # !! Contents within this block are managed by 'conda init' !!
             __conda_setup="$('/gpfs/u/home/BMHR/BMHRkmkh/scratch/miniconda3-x86/bin/conda' 'shell.bash' 'hook' 2> /dev/null)"
             if [ $? -eq 0 ]; then
                 eval "$__conda_setup"
             else
                 if [ -f "/gpfs/u/home/BMHR/BMHRkmkh/scratch/miniconda3-x86/etc/profile.d/conda.sh" ]; then
                     . "/gpfs/u/home/BMHR/BMHRkmkh/scratch/miniconda3-x86/etc/profile.d/conda.sh"
                 else
                     export PATH="/gpfs/u/home/BMHR/BMHRkmkh/scratch/miniconda3-x86/bin:$PATH"
                 fi
             fi
             unset __conda_setup
             # <<< conda initialize <<<
           fi
   fi

.. _sample-condarc:

Sample .condarc
^^^^^^^^^^^^^^^

There is a runtime configuration file, .condarc, in Anaconda.  You can use this file to specify the channels where conda looks for packages, etc.

For more information see https://docs.conda.io/projects/conda/en/latest/user-guide/configuration/use-condarc.html

IBM provides some repositories which contain packages built specifically for linux-ppc64le, linux-64 and noarch.   

*  WML-CE Conda repository at https://public.dhe.ibm.com/ibmdl/export/pub/software/server/ibm-ai/conda
*  WML-CE Early Access repository at https://public.dhe.ibm.com/ibmdl/export/pub/software/server/ibm-ai/conda-early-access/

For anaconda default repositories see https://docs.anaconda.com/anaconda/user-guide/tasks/using-repositories/

Depending on your AI workload, you may want to use IBM provided repositories to search for prebuilt packages before the default conda repositories.

For example, the following sample .condarc is for conda to search for packages in the early-access channel before go to the default conda repositories.

.. code:: bash

   channels:
   - https://public.dhe.ibm.com/ibmdl/export/pub/software/server/ibm-ai/conda-early-access/
   - defaults

The following .condarc is specifying that conda searches the wml-ce early access, the wml-ce, the powerai, the defaults and conda-forge in order for packages. 


.. code:: bash

   channels:
   - https://public.dhe.ibm.com/ibmdl/export/pub/software/server/ibm-ai/conda-early-access/
   - https://public.dhe.ibm.com/ibmdl/export/pub/software/server/ibm-ai/conda/
   - powerai
   - defaults
   - conda-forge

Troubleshooting Tips
^^^^^^^^^^^^^^^^^^^^

* When you get a disk I/O error, check disk quota for $HOME and barn. See https://docs.cci.rpi.edu/Frequently_Asked_Questions/#how-do-i-check-my-gpfs-quota-usage for how to.  For example, you want to know the quota of $HOME and the size of the files in $HOME:

.. code:: bash

   cd ~
   df -h .
   du -d1 -k



  

