.. _get-user-id-section:

How to get a  user id on AiMOS?
===============================


* If you already have an ID on AiMOS and want to be added to another project, you need to request the Project Sponsor/Project Investigator to send an emai to Lorraine Herger at herger@us.ibm.com.  The email should contain your current ID and the project ID that you want to be added.  The email can be used for the list of user id and the list for projects. For example:

::
  
  To: herger@us.ibm.com
  cc: <your email id>
  Subject: Add existing users to another project

  USER ID: BMHRxxxx, SROMxxxx
  PROJECT ID: CADS, ADCS


* If you are a first time user, you need to fill out the following forms, sign and send them to herger@us.ibm.com.

CCI User Information
^^^^^^^^^^^^^^^^^^^^

https://secure.cci.rpi.edu/wiki/images/b/b1/CCI_User_Information_20140612.pdf

CCI User Responsibility Agreement
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

https://secure.cci.rpi.edu/wiki/images/b/b3/CCI_User_Responsibility_Agreement_20140612.pdf


Once the forms are processed, you will receive emails from **HPCman <hpcman@ccni.rpi.edu>** for your account ID and password reset token. The next step is to :ref:`set-password`.

**IMPORTANT:** You have 24 hours to reset your password.  If you miss it, you need to send an email to support@ccni.rpi.edu to request a new password reset token.

.. _set-password:

Set your password
^^^^^^^^^^^^^^^^^

You will receive the link similar to this, https://secure.cci.rpi.edu/password/?a=XXXXXXXXXXXXXXXX, where XXXXXXXXXXXXXXXX is your reset token. You need to use the link to reset your password.  After reset the password, the next step is to :ref:`set-challenge`.

.. _set-challenge:

Set the Challenge Word
^^^^^^^^^^^^^^^^^^^^^^

The next step is choose and set the Challenge Word: https://secure.cci.rpi.edu/challenge/

Enter your User ID, your newly reset password, and the challenge word twice, then click "Set Challenge Word".  You are ready for the next step :ref:`set-pic`.

.. _set-pic:

Set the Personal Identification Code (PIC)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The last step is to choose the Personal Identification code (PIC). The PIC is case-sensitive and is made up of at least 4 numbers and/or letters. No special characters may be used. Do not use your bank PIN, account name, first or last name, or organization.

* Install "Google Authenticator" app on your mobil device.

* Go to https://secure.cci.rpi.edu/totp.

    * Enter your User ID, the Password, the Challenge Word, the chosen PIC, then "Click Setup TOTP".
    * You will get a QR code on the webpage.

* Go to the Google Authenticator app on your mobile device and scan the QR code.

You now have everything you need to login to a landing pad node.

