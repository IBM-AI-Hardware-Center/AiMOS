.. _access-aimos:

Access to AiMOS
===============

This section describes the steps for you to apply for a user ID and the process for log in to AiMOS.

.. _get-user-id-section:


Apply for a user ID on AiMOS
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

* If you already have an ID on AiMOS and want to be added to another project, you need to request the Project Sponsor/Project Investigator to send an emai to Lorraine Herger at herger@us.ibm.com.  The email should contain your current ID and the project ID that you want to be added.  The email can be used for the list of user id and the list for projects. For example:

::
  
  To: herger@us.ibm.com
  cc: <your email id>
  Subject: Add existing users to another project

  USER ID: BMHRxxxx, SROMxxxx
  PROJECT ID: CADS, ADCS


* If you are a first time user, you need to fill out the following forms, sign and send them to herger@us.ibm.com.

CCI User Information
++++++++++++++++++++

https://secure.cci.rpi.edu/wiki/assets/forms/CCI_User_Information.pdf

CCI User Responsibility Agreement
+++++++++++++++++++++++++++++++++

https://secure.cci.rpi.edu/wiki/assets/forms/CCI_User_Responsibility_Agreement.pdf

Once the forms are processed, you will receive emails from **HPCman <hpcman@ccni.rpi.edu>** for your account ID and password reset token. The next step is to :ref:`set-password`.

**IMPORTANT:** You have 24 hours to reset your password.  If you miss it, you need to send an email to support@ccni.rpi.edu to request a new password reset token.

.. _set-password:

Set your password
+++++++++++++++++

You will receive the link similar to this, https://secure.cci.rpi.edu/password/?a=XXXXXXXXXXXXXXXX, where XXXXXXXXXXXXXXXX is your reset token. You need to use the link to reset your password. Please note that you have 24 hours to reset your password after you receive the email. If you miss it, you need to send an email to support@ccni.rpi.edu to request for a new password reset token.  After reset the password, the next step is to :ref:`set-challenge`.

.. _set-challenge:

Set the Challenge Word
++++++++++++++++++++++

The next step is choose and set the Challenge Word: https://secure.cci.rpi.edu/challenge/

Enter your User ID, your newly reset password, and the challenge word twice, then click "Set Challenge Word".  You are ready for the next step :ref:`set-pic`.

.. _set-pic:

Set the Personal Identification Code (PIC)
++++++++++++++++++++++++++++++++++++++++++

The last step is to choose the Personal Identification code (PIC). The PIC is case-sensitive and is made up of at least 4 numbers and/or letters. No special characters may be used. Do not use your bank PIN, account name, first or last name, or organization.

* Install "Google Authenticator" app on your mobil device.

* Go to https://secure.cci.rpi.edu/totp.

    * Enter your User ID, the Password, the Challenge Word, the chosen PIC, then "Click Setup TOTP".
    * You will get a QR code on the webpage.

* Go to the Google Authenticator app on your mobile device and scan the QR code.

You now have everything you need to login to a landing pad node.


Join aimos slack channel
++++++++++++++++++++++++

**IMPORTANT:**  Do not forget to join the aimos slack channel for information, questions and answers. Here are the list of the aimos slack channels:


* #aimos for IBM Researchers.

* #aimos_cleveland_clinic-guest

* #aimos_kla-guest

* #aimos_tel-guest

* #aimos_synopsys-guest


You may need to send an email to Lorraine Herger (herger@us.ibm.com) to request for joining the slack channel.

.. _how-to-login:

Login to AiMOS
^^^^^^^^^^^^^^

The assumption is that you have already obtained your user ID for AiMOS.  If that is not the case,  please see :ref:`get-user-id-section`.

The steps are ssh to one of the landing pad nodes, then from there ssh to one of the front end nodes.  For the list of the landing pad nodes and front end nodes, please see :ref:`what-is-aimos`

ssh to a landing pad node
+++++++++++++++++++++++++

First you need to ssh to one of the landing pad nodes. There are four(4) landing pad nodes: 

* blp01.ccni.rpi.edu
* blp02.ccni.rpi.edu
* blp03.ccni.rpi.edu
* blp04.ccni.rpi.edu. 

For PIC+Token, enter your chosen PIC that you have set in the previous step and the token from the Google Authenticator app on your mobile device. For example: 

.. figure:: authenticator.png

**Note:** do not enter + and space.  


For example:

::

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

If this is the first time you login to one of the landing pad nodes using your user id, it is strongly recommended that you set up passwordless and proxy.  For how to see :ref:`setup-environment`. The next step is to login to a front end node.

ssh to a front end node
+++++++++++++++++++++++

From the landing pad node, you ssh to either the DCS front end node or the NPL front end note.  There are two DCS front end nodes:

* dcsfen01 
* dcsfen02

There is only one NPL front end node:

* nplfen01

If you have set up the passwordless then you can ssh to the front end node without the pasword prompt.  
If you need information on how to set up passwordless, please see :ref:`setup-environment`.

For example, you ssh to the dcsfen01:

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


Or you ssh to the nplfen01 node.

.. code:: bash

   [BMHRkmkh@blp01 ~]$ ssh nplfen01
   Last login: Thu Jun 11 14:40:36 2020 from blp01.ccni.rpi.edu
   (base) [BMHRkmkh@npl41 ~]$

