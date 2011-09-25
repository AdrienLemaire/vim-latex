I created this repo, hoping that I'd be able to use the github pull request
feature with the remote sourceforge master project, but it didn't work.

The proper way to do a request from a read-only git repository is::

    $ git format-patch --cover-letter -M source/master -o outgoing/
    $ vim outgoing/0000-*
    $ git send-email outgoing/*

.. note:: here source/master because I created a source branch which points to
    the sourceforge repo


I updated my .gitconfig with the following::

    [sendemail]
        smtpencryption = tls
        smtpserver = smtp.gmail.com
        smtpuser = lemaire.adrien@gmail.com
        smtpserverport = 587
