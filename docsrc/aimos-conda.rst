.. _install-conda:

How to install the conda environment?
=====================================

Conda is not installed by default on AiMOS at the system level.  If you need the conda environment for your workload, you will need to install and set up in your environment.

IMPORTANT: Make sure that you set up the proxy before you proceed to the next step. For how to see :ref:`setup-environment`.

Download the the Miniconda3 installer if needed.

.. code:: bash

  wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-ppc64le.sh


Install the miniconda environment to scratch directory.

.. code:: bash

  [BMHRkmkh@dcsfen01 ~]$ bash Miniconda3-latest-Linux-ppc64le.sh -p ~/scratch/miniconda3
  
  Welcome to Miniconda3 4.7.12
  
  In order to continue the installation process, please review the license agreement.
  Please, press ENTER to continue
  >>>
  ...
  Do you accept the license terms? [yes|no]
  [no] >>> yes
  
  Miniconda3 will now be installed into this location:
  /gpfs/u/home/BMHR/BMHRkmkh/scratch/miniconda3
  
    - Press ENTER to confirm the location
    - Press CTRL-C to abort the installation
    - Or specify a different location below
  
  [/gpfs/u/home/BMHR/BMHRkmkh/scratch/miniconda3] >>>
  PREFIX=/gpfs/u/home/BMHR/BMHRkmkh/scratch/miniconda3
  Unpacking payload ...
  Collecting package metadata (current_repodata.json): done
  Solving environment: done
  
  ## Package Plan ##
  
    environment location: /gpfs/u/home/BMHR/BMHRkmkh/scratch/miniconda3
  
    added / updated specs:
      - _libgcc_mutex==0.1=main
      - asn1crypto==1.2.0=py37_0
      - ca-certificates==2019.10.16=0
  ...
    yaml               pkgs/main/linux-ppc64le::yaml-0.1.7-h1bed415_2
    zlib               pkgs/main/linux-ppc64le::zlib-1.2.11-h7b6447c_3
  
  
  Preparing transaction: done
  Executing transaction: done
  installation finished.
  Do you wish the installer to initialize Miniconda3
  by running conda init? [yes|no]
  [no] >>> yes
  no change     /gpfs/u/home/BMHR/BMHRkmkh/scratch/miniconda3/condabin/conda
  no change     /gpfs/u/home/BMHR/BMHRkmkh/scratch/miniconda3/bin/conda
  no change     /gpfs/u/home/BMHR/BMHRkmkh/scratch/miniconda3/bin/conda-env
  no change     /gpfs/u/home/BMHR/BMHRkmkh/scratch/miniconda3/bin/activate
  no change     /gpfs/u/home/BMHR/BMHRkmkh/scratch/miniconda3/bin/deactivate
  no change     /gpfs/u/home/BMHR/BMHRkmkh/scratch/miniconda3/etc/profile.d/conda.sh
  no change     /gpfs/u/home/BMHR/BMHRkmkh/scratch/miniconda3/etc/fish/conf.d/conda.fish
  no change     /gpfs/u/home/BMHR/BMHRkmkh/scratch/miniconda3/shell/condabin/Conda.psm1
  no change     /gpfs/u/home/BMHR/BMHRkmkh/scratch/miniconda3/shell/condabin/conda-hook.ps1
  no change     /gpfs/u/home/BMHR/BMHRkmkh/scratch/miniconda3/lib/python3.7/site-packages/xontrib/conda.xsh
  no change     /gpfs/u/home/BMHR/BMHRkmkh/scratch/miniconda3/etc/profile.d/conda.csh
  modified      /gpfs/u/home/BMHR/BMHRkmkh/.bashrc

  ==> For changes to take effect, close and re-open your current shell. <==
  
  If you'd prefer that conda's base environment not be activated on startup,
     set the auto_activate_base parameter to false:
  
  conda config --set auto_activate_base false
  
  Thank you for installing Miniconda3!
  [your-id@dcsfen01 ~]$
  [your-id@dcsfen01 ~]$ source .bashrc
  (base) [your-idh@dcsfen01 ~]$

  
Now you have the base conda installed and activated in your environment.