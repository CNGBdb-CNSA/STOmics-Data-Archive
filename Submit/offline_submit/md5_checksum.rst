MD5 Checksum
============

This is a 32-character alphanumeric string (e.g. 7da8a01243d3ac4a4f0aa02a172bd476) that can be computed for each file with native command line tools `md5` (**Mac OS X**) or `md5sum` (**Linux**).

For **Windows** users, there are several ways.

1. Using command line program for Windows

   - Press the Windows icon + R, the following interface appears, enter `cmd` to open the program.

     .. image:: ../images/open_cmd.png
     .. image:: ../images/windows_cmd.png

   - Enter the following command to calculate the MD5 value:

     .. code:: Linux

       CertUtil -hashfile Path\filename MD5

   For example,

   .. image:: ../images/cmd_example.png

2. Using Windows PowerShell

   Open Windows PowerShell, enter the following command to calculate the MD5 value:

   .. code:: Linux

     Get-FileHash Path\filename -Algorithm MD5| Format-List

   For example,

   .. image:: ../images/windows_powershell.png

3. Using the third party tools, e.g. `Fsum Frontend <http://sourceforge.net/projects/fsumfe/>`_.
