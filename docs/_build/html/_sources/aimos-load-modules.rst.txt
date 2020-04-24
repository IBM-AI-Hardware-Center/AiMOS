.. _load-module:

How to load different modules for your development and testing?
===============================================================

In AiMOS environment, you can use **module** to load the required tools and libraries for your development and testing.

List the available modules on the node:

.. code:: bash

  (base) [your-id@dcsfen01 ~]$ module available
  
  ------------------------------- /gpfs/u/software/ppc64le-rhel7/modulefiles --------------------------------
     automake/1.16.1 (S)      cmake/3.14.6  (S)    parmetis/4.0.3/xl (T)      xl/16.1.1
     bazel/0.17.2/1  (T)      gcc/6.4.0/1          pocl/1.2/1        (T)      xl_r/13     (O)
     bazel/0.18.1/1  (T,D)    gcc/6.5.0/1          spectrum-mpi/10.3 (T)      xl_r/16     (T,D)
     bazel/0.18.0/1  (T)      gcc/7.4.0/1          swig/3.0.12_1     (T)      xl_r/16.1.1
     bazel/0.21.0/1  (T)      gcc/8.1.0/1          valgrind/3.15.0   (S)
     ccache/3.5/1    (T)      gcc/8.2.0/1   (D)    xl/13             (O)
     clang/7.0.0/1   (T)      hwloc/2.0.2/1 (T)    xl/16             (T,D)
  
    Where:
     O:  Obsolete
     T:  Testing
     S:  Stable
     D:  Default Module

  Module defaults are chosen based on Find First Rules due to Name/Version/Version modules found in the module tree.
  See https://lmod.readthedocs.io/en/latest/060_locating.html for details.
  
  Use "module spider" to find all possible modules and extensions.
  Use "module keyword key1 key2 ..." to search for all possible modules matching any of the "keys".
  

For example, you want to load cmake module and spectrum_mpi module

.. code:: bash

  (base) [your-id@dcsfen01 ~]$ module load  cmake/3.14.6
  (base) [your-id@dcsfen01 ~]$ which cmake
  alias cmake='cmake3'
          /usr/bin/cmake3
  (base) [your-id@dcsfen01 ~]$ which cmake3
  /usr/bin/cmake3
  (base) [your-id@dcsfen01 ~]$ module load spectrum-mpi
  (base) [your-id@dcsfen01 ~]$ which mpirun
  /opt/ibm/spectrum_mpi/bin/mpirun

For more information see https://secure.cci.rpi.edu/wiki/index.php?title=Modules