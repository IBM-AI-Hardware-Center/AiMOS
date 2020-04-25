Slurm Resource Manager and Job Scheduler in AiMOS
=================================================

`Slurm <https://slurm.schedmd.com/overview.html>`_ (used to be \ **S**\imple \ **L**\inux \ **U**\tility for \ **R**\esource \ **Ma**\nagement) is the cluster management and job scheduler for AiMOS.

The fairshare allocation is used in the environment:

.. figure:: AiMOS-allocation2.png

* Each key partner (e.g., IBM, RPI) is given a fixed slice of AiMOS expressed as a percentage of the whole system. 
* Within a key partner’s “slice”, group projects are defined.
* By default, each project gets a fair share of the overall partner level slice.
* Inside each project, users accounts are created.
* By default, each user gets a fair share of the overall group project level slice

For more information see 
https://secure.cci.rpi.edu/wiki/index.php?title=Slurm

For the complete list of SLURM manpage, see https://slurm.schedmd.com/man_index.html

For the summary for SLURM commands and options, see https://slurm.schedmd.com/pdfs/summary.pdf

