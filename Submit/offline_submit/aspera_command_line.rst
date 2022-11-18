Aspera Command Line
===================

You may use the following command to upload files via Aspera Command-Line:

.. code-block:: Linux

   ascp -i <path/to/key_file> -P33001 -QT -l100m -k1 -d <path/to/folder/containing files> aspera_*****@183.239.175.39:/

where:

- ``<path/to/key_file>`` must be an absolute path, e.g.: /home/keys/aspera.openssh
- ``<path/to/folder/containing files>`` needs to specify the local folder that contains all of the files to upload.

Get the `key file <https://db.cngb.org/cnsa/ajax/get_aspera_key/>`_. Please do not share this key file. Do not include this information or key file on a public page.

If you upload data files and do not submit them on the web interface, they will be automatically deleted two months according to the database record.

**Stay tuned for more useful upload functions!**
