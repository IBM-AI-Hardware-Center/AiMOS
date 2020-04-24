.. _install-jupyter:

How to install Jupyter notebook?
================================

IMPORTANT: Make sure that you set up the proxy before you proceed to the next step.  For how to see :ref:`setup-environment`.


It is recommended to install `Jupyter notebook <https://jupyter.org/install.html>`_ in a miniconda environment which includes a minimal Python and conda installation.  You can install Jupyter notebook via conda install or pip install. For how to install conda enviroment see :ref:`install-conda`.


If you plan to use the AI framework with your notebook, make sure that you install Jupyter notebook in the conda environment that includes the AI framework.  For example, if you want to use the AI frameworks that are included in the WML-CE, then you need to install Jupyter notebook in the environment that WML-CE was installed.

.. code:: bash

  conda install -c conda-forge notebook


Or

.. code:: bash

  pip install notebook


For example:

.. code:: bash

  (base) [your-id@dcsfen01 wmlce-1.7.0]$ conda install -c conda-forge notebook
  Collecting package metadata (current_repodata.json): done
  Solving environment: done
  
  ## Package Plan ##
  
    environment location: /gpfs/u/home/BMHR/BMHRkmkh/scratch/miniconda3
  
    added / updated specs:
      - notebook
  
  
  The following packages will be downloaded:

      package                    |            build


Verify the notebook was installed.

.. code:: bash

  (base) [your-id@dcsfen01 wmlce-1.7.0]$ conda list | grep notebook
  notebook                  6.0.3                    py37_0    conda-forge

