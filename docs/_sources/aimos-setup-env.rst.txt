.. _setup-environment:

Setting up the environment 
==========================

The following sections are the steps for setting up your environment.

.. _setup-passwordless:

Setting up passwordless
^^^^^^^^^^^^^^^^^^^^^^^

It is strongly recommended that you set up the passwordless to login to the front end nodes and compute nodes.  This is particularly required if you are running MPI workload.  You only need to do this once.
The process consists of two steps: 

* Generate the key using ssh-keygen command.
* Concatenate the generated key to the authorized_keys file.
 
The following example assumes you already log in to either one of the landing pad nodes or one of the front end nodes. 

.. code:: bash

   $ ssh-keygen -t rsa
   Generating public/private rsa key pair.
   Enter file in which to save the key (/gpfs/u/home/BMHR/BMHRkmkh/.ssh/id_rsa):
   /gpfs/u/home/BMHR/BMHRkmkh/.ssh/id_rsa already exists.
   Overwrite (y/n)? y
   Enter passphrase (empty for no passphrase):
   Enter same passphrase again:
   Your identification has been saved in /gpfs/u/home/BMHR/BMHRkmkh/.ssh/id_rsa.
   Your public key has been saved in /gpfs/u/home/BMHR/BMHRkmkh/.ssh/id_rsa.pub.
   The key fingerprint is:
   SHA256:I7OYesm4IUs9vHbtXoYi4vy7dAOt9FMPJoQ8ssiibcI 
   BMHRkmkh@dcsfen01
   The key's randomart image is:
   +---[RSA 2048]----+
   |                 |
   |  . .            |
   | . + .           |
   |o o +            |
   |oo o oo+S        |
   |+.+ +o+++.       |
   |+E+XoBo. +       |
   |+=++O.+.o        |
   |.o=B+ oo         |
   +----[SHA256]-----+

   $ cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
 

.. _setup-proxy: 
 
Setting up proxy
^^^^^^^^^^^^^^^^

It is strongly recommended that you set up the proxy by adding the following lines to your .bashrc. You only need to do this once.

.. code:: bash

   export http_proxy=http://proxy:8888
   export https_proxy=$http_proxy

Do not forget to source your .bashrc for this to take affect.
