ds-down
=======

ds-down is a Python 3 program to send URLs and local files to Synology
DownloadStation using aforementioned DownloadStations Web API (`API pdf`_).

The main intended use-case is from console and a desktop file for xdg-open or
similar tools is provided.

Example config_ file:

.. code-block:: ini

    # Example config file, by default it should be located at:
    # ~/.config/ds-down.conf

    username     = admin
    host         = https://192.168.1.10:5001
    passwordeval = gpg --no-tty -d ~/.passwords/synology-admin.gpg

Examples
--------

Send a magnet link to the DownloadStation:

.. code-block:: bash

    $ ds-down 'magnet:?xt=urn:btih:dbd7d976a5bf566504357bf9f543a37d3513e4df&dn=archlinux-2014.07.03-dual.iso&tr=udp://tracker.archlinux.org:6969&tr=http://tracker.archlinux.org:6969/announce'

Send a locally stored torrent file to the DownloadStation:

.. code-block:: bash

    $ ds-down 'archlinux-2014.07.03-dual.iso.torrent'


Install
-------

Example of a simple user install with from source:

.. code-block:: bash

    python3 setup.py install --exec_name="ds_down" --user

The executable console script name can be controlled with the ´--exec_name=´
argument. The default is ´ds_down´. The executable script in this example is
placed in ´$HOME/.local/bin´ which can be added to the PATH variable if needed.
This also installs needed dependencies.

PyPI Install
------------

Alternatively last published version can be installed from PyPI_ with pip:

.. code-block:: bash

    pip3 install --user ds-down



.. _`API pdf`: http://ukdl.synology.com/download/Document/DeveloperGuide/Synology_Download_Station_Web_API.pdf
.. _config: https://github.com/wor/ds-down/blob/master/ds-down.conf
.. _PyPI: https://pypi.python.org/pypi/ds-down
