.. _request-nvme:

How to request for NVMe storage on the compute nodes?
=====================================================

To request NVMe storage, specify --gres=nvme with your Slurm commands. This can be combined with other requests, such as GPUs. When the first job step starts, the system will initialize the storage and create the path /mnt/nvme/uid_${SLURM_JOB_UID}/job_${SLURM_JOBID}.

.. code:: bash

  (base) [your-id@dcsfen01 ~]$  salloc -N 1 --gres=gpu:6 --gres=nvme -t 30
  salloc: Granted job allocation 64444
  (base) [your-id@dcsfen01 ~]$ squeue
               JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON)
               64444       dcs     bash BMHRkmkh  R       0:11      1 dcs055
  (base) [your-id@dcsfen01 ~]$ ssh dcs055
  Warning: Permanently added 'dcs055,172.31.236.55' (ECDSA) to the list of known hosts.
  (base) [your-id@dcs055 ~]$
  (base) [your-id@dcs055 ~]$ df -h
  Filesystem      Size  Used Avail Use% Mounted on
  devtmpfs        243G     0  243G   0% /dev
  tmpfs           256G   64K  256G   1% /dev/shm
  tmpfs           256G   25M  256G   1% /run
  tmpfs           256G     0  256G   0% /sys/fs/cgroup
  rootfs          256G  7.6G  249G   3% /
  rw              256G   64K  256G   1% /.sllocal/log
  gpfs.u          1.1P  387T  640T  38% /gpfs/u
  /dev/nvme0n1    1.5T   77M  1.5T   1% /mnt/nvme
  (base) [your-id@dcs055 job_64444]$ pwd
  /mnt/nvme/uid_6112/job_64444


**NOTE:** The NVMe storage is not persistent between allocations.