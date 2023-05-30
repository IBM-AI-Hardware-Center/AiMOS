.. _access-aimos:

Access to AiMOS
===============

This section describes the steps for you to apply for a user ID and the process for log in to AiMOS. Access to AiMOS is limited to AI Hardware center members and partners.

.. _get-user-id-section:


Apply for a user ID on AiMOS
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**IMPORTANT:** Please include your **first name initial** and **last name** in the name of all files that you send to Kaoutar El maghraoui and Mickey Song.  For example:

   - **CCI_User_Information_MSong**.pdf
   - **CCI_User_Responsibility_Agreement_MSong**.pdf
   - **CCI_Project_Information_MSong.pdf**.pdf

* If you are a first time user, you need to fill out the following forms, sign and send them to Kaoutar El maghraoui(Email: kelmaghr@us.ibm.com) for approval and cc to Mickey Song(Email: msong@us.ibm.com).  Also, provide the following:

  * If you are joining an existing project, please provide the 4 letter ID of the project, and the approval of the project leader/ PI.  CC'ing the PI on the email is sufficient.
  * If you are requesting a new project, then provide the following information in your email, along with your two completed forms:

      - Project Title:
      - Short Project Description:

* If you already have an AiMOS ID, and are requesting access to an existing project, only provide the following:

  * Your current AiMOS user ID.
  * 4 letter ID of the project you wish to join.
  * Approval of the project lead / PI to join the project.  CC'ing the PI on the email is sufficient.  For example:

::
  
  To: kelmaghr@us.ibm.com
  cc: <PI email id>
  Subject: Add existing users to another project

  USER ID: BMHRxxxx, SROMxxxx
  PROJECT ID: CADS, ADCS


CCI User Information
++++++++++++++++++++
https://docs.cci.rpi.edu/assets/forms/CCI_User_Information.pdf

CCI User Responsibility Agreement
+++++++++++++++++++++++++++++++++
https://docs.cci.rpi.edu/assets/forms/CCI_User_Responsibility_Agreement.pdf

CCI Project Information
+++++++++++++++++++++++++++++++++
https://docs.cci.rpi.edu/assets/forms/CCI_Project_Information.pdf


**IMPORTANT:** Please include your **first name initial** and **last name** in the name of all files that you send to Kaoutar El maghraoui for approval.  For example:

* **CCI_User_Information_KTran**.pdf 
* **CCI_User_Responsibility_Agreement_KTran**.pdf
* **CCI_Project_Information.pdf**.pdf

Once the forms are processed, you will receive emails from **HPCman <hpcman@ccni.rpi.edu>** for your account ID and password reset token. The next step is to :ref:`set-password`.

**IMPORTANT:** You have 24 hours to reset your password.  If you miss it, you need to send an email to support@ccni.rpi.edu to request a new password reset token.

.. _set-password:

Set your password
+++++++++++++++++

You will receive the link similar to this, https://secure.cci.rpi.edu/password/?a=XXXXXXXXXXXXXXXX, where XXXXXXXXXXXXXXXX is your reset token. You need to use the link to reset your password. Please note that you have 24 hours to reset your password after you receive the email. If you miss it, you need to send an email to support@ccni.rpi.edu to request for a new password reset token.  After reset the password, the next step is to :ref:`set-challenge`.


.. _set-duo:

setup Two Factor authentication with Duo
++++++++++++++++++++++++++++++++++++++++

Login to CCI client portal at https://secure.cci.rpi.edu/client/ . You will be prompted to setup Two Factor authentication with Duo.
Once you have set a password and enrolled in Duo you can login to our systems usings SSH.

If you work in multiple CCI projects each will have a unique username, but will share the same password and Duo enrollment. If you have only one project, you can use existing password to setup DUO.

.. _set-challenge:

Set the Challenge Word
++++++++++++++++++++++

The next step is choose and set the Challenge Word: https://secure.cci.rpi.edu/challenge/

Enter your User ID, your newly reset password, and the challenge word twice, then click "Set Challenge Word".  


.. _Re_Activate_User_Account:

Re-activate User Account
++++++++++++++++++++++++

Users need to re-activate their account in one of the following scenarios

**Re-activate Account**

* Deactivated account.  A user account will be deactivated after 3 months without using.

Step 1) Send an email to support@ccni.rpi.edu to request for a new password reset token.

Step 2) Set the Challenge Word

Step 3) Set the Duo. Reinstall "Duo Mobile" if changed a new phone.



.. _Join_AiMOS_Slack_Channel:

Join aimos slack channel
++++++++++++++++++++++++

**IMPORTANT:**  Do not forget to join the aimos slack channel for information, questions and answers. Here are the list of the aimos slack channels:


* #aimos for IBM Researchers.

* #aimos_cleveland_clinic-guest

* #aimos_kla-guest

* #aimos_tel-guest

* #aimos_synopsys-guest

All IBM users who are not in the IBM Research Division, or users who are external to IBM,  will need to send a request to join email to Kaoutar El maghraoui(Email: kelmaghr@us.ibm.com).

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

SSh Example:

ssh BMHRmksg@blp03.ccni.rpi.edu

Password: 
Duo two-factor login for mksg

Enter a passcode or select one of the following options:

 1. Duo Push to XXX-XXX-8058

Passcode or option (1-1): 

After input your password and select the phone number, on your phone open Duo app and authorize the login. 


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
  **     https://docs.cci.rpi.edu                         **
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
  **     https://docs.cci.rpi.edu                         **
  **                                                             **
  **     Use is subject to the terms of the policy for           **
  **     Acceptable Use of CCI Resources.                        **
  **                                                             **


Or you ssh to the nplfen01 node.

.. code:: bash

   [BMHRkmkh@blp01 ~]$ ssh nplfen01
   Last login: Thu Jun 11 14:40:36 2020 from blp01.ccni.rpi.edu
