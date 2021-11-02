.. _AI_Hardware_Toolkit:
   
Analog AI Hardware Toolkit(AIHW)
================================

In traditional hardware architecture, computation and memory are siloed in different locations. Information is moved back and forth between computation and memory units every time an operation is performed, creating a limitation called the von Neumann bottleneck.

IBM Research has created phase-change memory (PCM) elements that allow computations to happen in the same location where data is stored. This new type of memory eliminates the need to move data from storage to compute. The memory is also non-volatile, meaning that no power is necessary to keep the data stored. For more information, please read `here <https://analog-ai-demo.mybluemix.net/>`_ 

IBM Analog Hardware Acceleration Kit is an open source Python toolkit for exploring and using the capabilities of in-memory computing devices in the context of artificial intelligence. The toolkit consists of two main components:

.. _pytorch_integration:

* **Pytorch integration**

A series of primitives and features that allow using the toolkit within PyTorch


.. _analog_devices_simulator:

* **Analog devices simulatoion**

A high-performant (CUDA-capable) C++ simulator that allows for simulating a wide range of analog devices and crossbar configurations by using abstract functional models of material characteristics with adjustable parameters. 


.. _getting_started:

Getting Started
^^^^^^^^^^^^^^^

Install Analog Hardware Acceleration Kit

.. code:: bash

   [BMHRkmkh@dcsfen01]$ pip install aihwkit


**Inatalation Verification** 

    Please follow `IBM Analog Hardware Acceleration Kit’s documentation <https://aihwkit.readthedocs.io/en/latest/install.html>`_ 

   
Training Analog Model
^^^^^^^^^^^^^^^^^^^^^

Copy Sample Code

.. code:: bash

   mkdir ~/scratch/analog-ai
   mkdir ~/scratch/analog-ai/results

Load Aihwkit Environment Variables

.. code:: bash

   cp /gpfs/u/locker/201/CABS/analog-aihwkit/aihwkit/0.2.1/examples/* ~/scratch/analog-ai/

Run Ai Training Sample Code

.. code:: bash

   [BMHRmksg@npl06 analog-ai]$ conda activate /gpfs/u/software/npl-conda/aihwkit_v3_67abd25

   (/gpfs/u/software/npl-conda/aihwkit_v3_67abd25) [BMHRmksg@npl41 analog-ai]$ python 04_lenet5_training.py
   LeNet5(
     (feature_extractor): Sequential(
       (0): AnalogConv2d(1, 16, kernel_size=(5, 5), stride=(1, 1))
       (1): Tanh()
       (2): MaxPool2d(kernel_size=2, stride=2, padding=0, dilation=1, ceil_mode=False)
       (3): AnalogConv2d(16, 32, kernel_size=(5, 5), stride=(1, 1))
       (4): Tanh()
       (5): MaxPool2d(kernel_size=2, stride=2, padding=0, dilation=1, ceil_mode=False)
       (6): Tanh()
     )
     (classifier): Sequential(
       (0): AnalogLinear(in_features=512, out_features=128, bias=True, is_cuda=True)
       (1): Tanh()
       (2): AnalogLinear(in_features=128, out_features=10, bias=True, is_cuda=True)
     )
   )

   14:33:19 --- Started LeNet5 Example

   14:33:19 --- Started LeNet5 Example
   14:33:39 --- Epoch: 0   Train loss: 1.9726      Valid loss: 1.6097      Test error: 10.00%      Accuracy: 90.00%
   14:33:59 --- Epoch: 1   Train loss: 1.5619      Valid loss: 1.5278      Test error: 5.07%       Accuracy: 94.93%
   14:34:19 --- Epoch: 2   Train loss: 1.5214      Valid loss: 1.5083      Test error: 3.42%       Accuracy: 96.58%
   14:34:42 --- Epoch: 3   Train loss: 1.5066      Valid loss: 1.5001      Test error: 2.90%       Accuracy: 97.10%
   14:35:02 --- Epoch: 4   Train loss: 1.4995      Valid loss: 1.4950      Test error: 2.51%       Accuracy: 97.49%
   14:35:22 --- Epoch: 5   Train loss: 1.4950      Valid loss: 1.4911      Test error: 2.33%       Accuracy: 97.67%
   14:35:42 --- Epoch: 6   Train loss: 1.4915      Valid loss: 1.4884      Test error: 2.11%       Accuracy: 97.89%
   14:36:02 --- Epoch: 7   Train loss: 1.4889      Valid loss: 1.4875      Test error: 2.12%       Accuracy: 97.88%
   14:36:22 --- Epoch: 8   Train loss: 1.4866      Valid loss: 1.4847      Test error: 1.85%       Accuracy: 98.15%
   14:36:42 --- Epoch: 9   Train loss: 1.4846      Valid loss: 1.4835      Test error: 1.76%       Accuracy: 98.24%
   14:37:04 --- Epoch: 10  Train loss: 1.4834      Valid loss: 1.4849      Test error: 1.93%       Accuracy: 98.07%
   14:37:24 --- Epoch: 11  Train loss: 1.4822      Valid loss: 1.4820      Test error: 1.69%       Accuracy: 98.31%
   14:37:49 --- Epoch: 12  Train loss: 1.4811      Valid loss: 1.4818      Test error: 1.64%       Accuracy: 98.36%
   14:38:14 --- Epoch: 13  Train loss: 1.4803      Valid loss: 1.4808      Test error: 1.62%       Accuracy: 98.38%
   14:38:38 --- Epoch: 14  Train loss: 1.4795      Valid loss: 1.4801      Test error: 1.58%       Accuracy: 98.42%
   14:39:02 --- Epoch: 15  Train loss: 1.4785      Valid loss: 1.4794      Test error: 1.35%       Accuracy: 98.65%
   14:39:26 --- Epoch: 16  Train loss: 1.4777      Valid loss: 1.4797      Test error: 1.42%       Accuracy: 98.58%
   14:39:51 --- Epoch: 17  Train loss: 1.4771      Valid loss: 1.4790      Test error: 1.43%       Accuracy: 98.57%
   14:40:15 --- Epoch: 18  Train loss: 1.4767      Valid loss: 1.4797      Test error: 1.51%       Accuracy: 98.49%
   14:40:40 --- Epoch: 19  Train loss: 1.4763      Valid loss: 1.4787      Test error: 1.37%       Accuracy: 98.63%
   14:41:05 --- Epoch: 20  Train loss: 1.4756      Valid loss: 1.4791      Test error: 1.44%       Accuracy: 98.56%
   14:41:29 --- Epoch: 21  Train loss: 1.4752      Valid loss: 1.4788      Test error: 1.48%       Accuracy: 98.52%
   14:41:55 --- Epoch: 22  Train loss: 1.4746      Valid loss: 1.4779      Test error: 1.37%       Accuracy: 98.63%
   14:42:20 --- Epoch: 23  Train loss: 1.4742      Valid loss: 1.4777      Test error: 1.41%       Accuracy: 98.59%
   14:42:44 --- Epoch: 24  Train loss: 1.4742      Valid loss: 1.4777      Test error: 1.36%       Accuracy: 98.64%
   14:43:06 --- Epoch: 25  Train loss: 1.4738      Valid loss: 1.4774      Test error: 1.29%       Accuracy: 98.71%
   14:43:30 --- Epoch: 26  Train loss: 1.4732      Valid loss: 1.4775      Test error: 1.42%       Accuracy: 98.58%
   14:43:55 --- Epoch: 27  Train loss: 1.4729      Valid loss: 1.4776      Test error: 1.40%       Accuracy: 98.60%
   14:44:18 --- Epoch: 28  Train loss: 1.4727      Valid loss: 1.4793      Test error: 1.56%       Accuracy: 98.44%
   14:44:41 --- Epoch: 29  Train loss: 1.4724      Valid loss: 1.4781      Test error: 1.50%       Accuracy: 98.50%
   14:44:42 --- Completed LeNet5 Example

Copy results to your workstation

.. code:: bash

   scp BMHRmksg@blp01.ccni.rpi.edu:/gpfs/u/home/BMHR/BMHRmksg/scratch/analog-ai/results/LENET5/* .


Test Losses

.. figure:: test_losses.png

Test Error

.. figure:: test_error.png

More Examples
^^^^^^^^^^^^^
For more examples, please visit `github <https://github.com/IBM/aihwkit/tree/master/examples>`_
