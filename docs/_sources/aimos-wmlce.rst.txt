.. _install-wmlce:

How to install WML-CE (a.k.a PowerAI)?
======================================

Watson Machine Learning Community Edition (WML CE), formerly PowerAI, is a free, enterprise-grade software distribution that combines popular open source deep learning frameworks, efficient AI development tools, and accelerated IBM® Power Systems™ servers to take your deep learning projects to the next level.

For more information, see
https://developer.ibm.com/linuxonpower/deep-learning-powerai/releases/

**IMPORTANT:** 

* Make sure that you set up the proxy before you proceed to the next step.  For how to see 

* Conda is installed and activated. For how to see :ref:`install-conda`.


Set up ~/.condarc if needed.  Below is the example of .condarc file. You need replace *your-project* with your PROJECT ID and *<your-id>* with your ID.

.. code:: bash

  pkgs_dirs:
    - /gpfs/u/software/ppc64le-rhel7/.conda/pkgs
    - /gpfs/u/home/your-project/<your-id>/scratch/miniconda3/pkgs
    - /gpfs/u/home/your-project/<your-id>/.conda/pkgs
  channels:
    - https://public.dhe.ibm.com/ibmdl/export/pub/software/server/ibm-ai/conda
    - defaults

As a best practice, you should install WML-CE in a new conda environment (i.e. not the base environment).  That would enable you to have different versions of WML-CE.

For more information on how to install WML-CE, see https://www.ibm.com/support/knowledgecenter/SS5SF7_1.7.0/navigation/wmlce_install.htm

Create a new conda environment wmlce-1.7.0 using python version 3.6.

.. code:: bash

  conda create --name wmlce-1.7.0 python=3.6

Activate the created conda environment.

.. code:: bash

  conda activate wmlce-1.7.0


Install WML-CE version 1.7.0 which is the latest version at the time of this writting.

For automatically accept the license

.. code:: bash

  export IBM_POWERAI_LICENSE_ACCEPT=yes


* To install the whole powerai GPU packages in the created conda environment, run:

.. code:: bash

  conda install powerai


* To install the whole powerai GPU packages version 1.6.2

.. code:: bash

  conda install powerai=1.6.2


* To install the individual framework, such as pytorch or tensorflow.

For complete list of individual framework see https://www.ibm.com/support/knowledgecenter/SS5SF7_1.7.0/navigation/wmlce_install.htm

.. code:: bash

  conda install pytorch
  
Or

.. code:: bash

  conda install tensorflow-gpu


* To install powerai CPU packages in the created conda environment, run:

.. code:: bash

  conda install powerai-cpu


* To install RAPIDS packages, run:

.. code:: bash

  conda install powerai-rapids

