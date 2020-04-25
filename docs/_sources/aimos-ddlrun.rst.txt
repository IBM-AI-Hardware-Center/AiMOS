.. _distributed-run:

Example for using ddlrun to run a distributed job?
==================================================

This is the example for how to run tensorflow2_keras_mnist.py from `Horovod GitHub repo <https://github.com/horovod/horovod.git>`_ using `ddlrun <https://www.ibm.com/support/knowledgecenter/SS5SF7_1.7.0/navigation/wmlce_ddlrun.html>`_


Prerequisites:
^^^^^^^^^^^^^^

* Make sure that you set up the proxy before you proceed to the next step. For how to see :ref:`setup-environment`.

* Conda is installed and activated. For how to see :ref:`install-conda`.

* Access to channel https://public.dhe.ibm.com/ibmdl/export/pub/software/server/ibm-ai/conda/linux-ppc64le/ in the ~/.condarc file.  If not, you can use the following command to add it:

.. code:: bash

  conda config --add channels https://public.dhe.ibm.com/ibmdl/export/pub/software/server/ibm-ai/conda/linux-ppc64le/

Create a conda env
^^^^^^^^^^^^^^^^^^

For example:

.. code:: bash

  conda create -n ddl-env
  
After the ddl-env is created, you should be placed in that env.  If not, you need to run 

.. code:: bash

  conda activate ddl-env
 
Install additional packages
^^^^^^^^^^^^^^^^^^^^^^^^^^^

For this example, you need tensorflow version 2.x, ddl and horovod

.. code:: bash

  conda install tensorflow-gpu ddl horovod
  
Clone the Horovod GitHub repo 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code:: bash

  cd $HOME/scratch
  git clone https://github.com/horovod/horovod.git


Setting up the test environment
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code:: bash

  cd $HOME/scratch/horovod/examples
  mkdir logs
  mkdir hosts
  
Create a batch job
^^^^^^^^^^^^^^^^^^

This is the sample script that you can customize to your environment.  This script specifies that you want to have two nodes with 6GPU per node and 6 tasks per node.

.. code:: bash

  #!/bin/bash -x
  #SBATCH -J <jobname>
  #SBATCH -o <jobname>_%j.out
  #SBATCH -e <jobname>_%j.out
  #SBATCH --mail-type=ALL
  #SBATCH --mail-user=<your gmail email>
  #SBATCH --gres=gpu:6
  #SBATCH --nodes=2
  #SBATCH --ntasks-per-node=6
  #SBATCH --time=00:10:00
  
  logdir=~/scratch/horovod/examples/logs
  hostdir=~/scratch/horovod/examples/hosts
  codedir=~/scratch/horovod/examples
  codepath=$codedir/tensorflow2_keras_mnist.py

  srun hostname -s | sort -u > $hostdir/hosts.$SLURM_JOBID
  awk "{ print \$0 \"-ib\"; }" $hostdir/hosts.$SLURM_JOBID >$hostdir/tmp.$SLURM_JOBID
  mv $hostdir/tmp.$SLURM_JOBID $hostdir/hosts.$SLURM_JOBID

  ddlrun -v  -hostfile $hostdir/hosts.$SLURM_JOBID   python $codepath
  
  rm $hostdir/hosts.$SLURM_JOBID

Running the batch script
^^^^^^^^^^^^^^^^^^^^^^^^

This example will try to download the MNIST dataset from  https://storage.googleapis.com/tensorflow/tf-keras-datasets/mnist.npz.  However, AiMOS has limited access to the internet, hence this step will fail with the following error:

.. code:: bash

  Exception: URL fetch failure on https://storage.googleapis.com/tensorflow/tf-keras-datasets/mnist.npz: None -- Tunnel connection failed: 403 Filtered

To get around this limitation, you need to download and copy mnist.npz to your $HOME/.keras/datasets.  In addition, you need to  emulate this line of code:  tf.keras.datasets.mnist.load_data(path='mnist-%d.npz' % hvd.rank()).  In this example, you use two nodes with 6 GPU on each node and one task per GPU. Hence you will have 12 ranks start from 0.  So you need to do the following:

.. code:: bash

  cd $HOME/.keras/datasets
  cp mnist.npz mnist-0.npz
  cp mnist.npz mnist-1.npz
  cp mnist.npz mnist-2.npz
  cp mnist.npz mnist-3.npz
  cp mnist.npz mnist-4.npz
  cp mnist.npz mnist-5.npz
  cp mnist.npz mnist-6.npz
  cp mnist.npz mnist-7.npz
  cp mnist.npz mnist-8.npz
  cp mnist.npz mnist-9.npz
  cp mnist.npz mnist-10.npz
  cp mnist.npz mnist-11.npz
  
The next step is to run the script using **sbatch** command.  Make sure that you are in the ddl-env

.. code:: bash

  cd ~/scratch/horovod/examples
  sbatch ./tensorflow2-keras-mnist.py
  

Use the **squeue** command to check if the job is started.  Once it is running, you can tail -f the <jobname>_<jobid>.err for progress.

