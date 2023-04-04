mitxpro-oauth plugin for `Tutor <https://docs.tutor.overhang.io>`__
===================================================================================

This is a simple plugin that contains the necessary configuration settings for integrating a Tutor instance with an OL application that uses OAuth2. This was written specifically for `MITx Online <https://github.com/mitodl/mitxonline>`_ but should reasonably work with other things too (such as xPro). 

Specifically, this just adds a few things to the common settings but notably it will also disable the AuthN MFE. 

Installation and Usage
----------------------

::

    pip install git+git@github.com:mitodl/tutor-mitxpro-oauth.git
    tutor plugins enable mitxpro-oauth


Once you've installed the plugin, you will additionally need to add a ``private.txt`` to the tutor requirements. This should contain the following two packages:

::

    social-auth-mitxpro
    mitxpro-openedx-extensions


This goes in ``env/build/openedx/requirements`` in the root of your Tutor install (``$TUTOR_ROOT``) - what this is specifically will depend on your environment. Rebuild your ``openedx`` image after adding this. 

You'll also need to create third-party app configurations and access tokens and everything else that's necessary from within Django Admin/etc. on both sides of the system. An example of that is here: https://github.com/mitodl/mitxonline/blob/main/docs/source/configuration/open_edx.rst

License
-------

This software is licensed under the terms of the BSD 3-Clause license.