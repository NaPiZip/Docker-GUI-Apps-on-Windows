.. image:: https://stapp.space/content/images/2016/05/docker_header1.png
    :width: 72px
    :target: https://www.docker.com

Docker running GUI Applications on Windows
===
.. image:: https://img.shields.io/badge/Document%20Version-1.0.0-brightgreen.svg
  :target: https://github.com/NaPiZip/Docker_GUI_Apps_on_Windows

.. image:: https://img.shields.io/badge/Docker-17.05.0--ce-blue.svg
    :target: https://www.docker.com

.. image:: https://img.shields.io/badge/Cygwin%2FX-7.7-blue.svg
    :target: http://x.cygwin.com

This is a tutorial showing how to run graphical user interface applications
inside a Docker container on a Windows 10 host system using Cygwin/X.

The following programs are needed for the installation:

* `Cygwin/X`

* `Docker` (Docker is assumed to be installed and working correctly)

.. _Cygwin/X: https://x.cygwin.com
.. _Docker: https://www.docker.com


Installation
--------

1. Follow the instruction accordingly to this `link`.

.. _link: https://x.cygwin.com/docs/ug/setup.html#setup-cygwin-x-installing

2. Make sure to install the following packages:
    * xorg-server (required, the Cygwin/X X Server)
    * xorg-docs (optional, man pages)
    * xlaunch (optional, a wizard for starting X sessions)


Tutorial
-------------

* run XWin :0 -listen tcp -multiwindow

This will start an `X server` on Windows machine on your local machine.

* `magic`



.. _X server: https://jarekprzygodzki.wordpress.com/2016/07/11/running-linux-graphical-applications-in-docker-on-windows-with-cygwinx/
.. _magic: https://manomarks.github.io/2015/12/03/docker-gui-windows.html


Contributing
------------

To get started with contributing to mu GitHub repo, pleas contact me `Slack`.



.. _Slack: https://slack.com/
