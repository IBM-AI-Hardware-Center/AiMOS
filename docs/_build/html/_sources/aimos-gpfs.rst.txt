What is the GPFS disk space on the nodes?
=========================================

The same GPFS filesystems are mounted on all the landing pad nodes, the front end nodes and the compute nodes in AiMOS.


* Each project is given a 10 GiB quota for barn and a 10 GiB quota for home. Home is intended for long-term storage of configurations, scripts, etc. Barn is intended for medium-term storage.
* home directory contains a link to scratch, the user's personal scratch space.  It also contains a link to scratch-shared, the project's shared scratch space.
* scratch and scratch-shared are meant as a temporary staging area for performing computation. Performance in this directory will be better than in the home or barn areas. This space does not have a quota. However, it will periodically be purged of files that are not used (either by read or write operation) in the last 56 days.  WARNING: If purging files that are not used in the last 56 days is not sufficient to maintain enough working space, the RPI team may purge all files with advance warning.

For more information see https://secure.cci.rpi.edu/wiki/index.php?title=File_System

Due to the limit space of 10 GiB for $HOME, $HOME/barn and $HOME/barn-shared combined, it is best to use these directories to store configuration files, scripts, or small programs needed to customize the working environment. You should use $HOME/scratch and $HOME/scratch-shared for things that require more space. **NOTE:** $HOME/scratch-shared are visible and shared among the users in the same project.

.. code:: bash

  /gpfs
     /u
       /home
          /<PROJ>
              /<USER>
                  /barn
                  /barn-shared
                  /scratch
                  /scratch-shared
