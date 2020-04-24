How to login to AiMOS?
======================

The assumption is that you have already obtained your user ID for AiMOS.  If that is not the case,  please see :ref:`get-user-id-section`

The steps are ssh to one of the landing pad nodes, then from there ssh to one of the front end nodes.  For the list of the landing pad nodes and front end nodes, please see :ref:`what-is-aimos`

ssh to a landing pad node
^^^^^^^^^^^^^^^^^^^^^^^^^

First you need to ssh to one of the landing pad nodes. There are four(4) landing pad nodes: 

* blp01.ccni.rpi.edu
* blp02.ccni.rpi.edu
* blp03.ccni.rpi.edu
* blp04.ccni.rpi.edu. 

For PIC+Token, enter your chosen PIC that you have set in the previous step and the token from the Google Authenticator app on your mobile device. 

**Note:** do not enter + and space.  

For example:

.. code:: bash

  $ ssh your-id@blp01.ccni.rpi.edu
  PIC+Token:
  Password:
  Last login: Fri Mar  6 15:41:57 2020 from 70.113.9.236
  
               ** CCI SSH Gateway (Landing pad) **
  **                                                             **
  **     Please report all support and operation issues to       **
  **     support@ccni.rpi.edu                                    **
  **                                                             **
  **     On-line documentation for the systems can be found at:  **
  **     https://secure.cci.rpi.edu/wiki                         **
  **                                                             **
  **     CCI does not provide any data backup services. Users    **
  **     are responsible for their own data management and       **
  **     backup.                                                 **
  **                                                             **
  **     Use is subject to the terms of the policy for           **
  **     Acceptable Use of CCI Resources.                        **
  **                                                             **

If this is the first time you login to one of the landing pad nodes using your user id, it is strongly recommended that you set up passwordless and proxy.  For how to see :ref:`setup-environment`.

ssh to a front end node
^^^^^^^^^^^^^^^^^^^^^^^

From the landing pad node, you ssh to the one of the front end nodes.  There are two front end nodes:

* dcsfen01 
* dcsfen02 

If you have set up the passwordless then you can ssh to the front end node without the pasword prompt.  
If you need information on how to set up passwordless, please see :ref:`setup-environment`.

.. code:: bash

  [your-id@blp01 ~]$ ssh dcsfen01
  Last login: Fri Feb 28 11:43:56 2020 from 172.31.29.1

                     ** CCI DCS front-end node **
  **                                                             **
  **     Please report all support and operation issues to       **
  **     support@ccni.rpi.edu                                    **
  **                                                             **
  **     On-line documentation for the systems can be found at:  **
  **     https://secure.cci.rpi.edu/wiki                         **
  **                                                             **
  **     Use is subject to the terms of the policy for           **
  **     Acceptable Use of CCI Resources.                        **
  **                                                             **


