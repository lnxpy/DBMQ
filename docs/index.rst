DBMQ (Docker-based Message Queuing)
===================================

Docker-based Message Queuing (DBMQ) is an efficient way to run the pre-built configurations on the build process of Dockerfiles.
Once you have finished configuring, you will be able to create your images based on your configurations.

.. warning::
   DBMQ is fully stable on Linux-based distributions and there is no guarantee that this tool works as properly
   as what it does on the Linux machines on Windows machines.

Why DBMQ is Needed
------------------

This system locates between the user and the Docker service. You config your requirements and let this automated system to provide them to you.
You don't need to be a genius in Docker, just keep configuring.

.. toctree::
   :caption: Table of Contents:

   topics/webserver_configurations.rst

Installation
------------

This installation process is valid on the Linux-based distributions so that you better to find the equivalent commands on other machines.
The things you need to do is to install ``Docker`` engine on your machine and make sure you have ``python>=3.8`` available on your machine.
We will catch all steps one by one. Let's have a general view on the way that we want to get through. First of all, we will install Docker and then,
we will take a closer look on python and ``virtualenvs``.

.. note::
   We are going to install all dependencies through an isolated environment called ``env``.

Docker Installation
~~~~~~~~~~~~~~~~~~~

Depending on your distribution, you need to find the way that you can install Docker on your machine. Here is the `Official Docker Installation Guide
<https://docs.docker.com/engine/install/ubuntu/>`_ that will help you to setup Docker on your distribution. The focuses are more on DBMQ and all its
dependencies.

DBMQ Installation
~~~~~~~~~~~~~~~~~

In this section, you need to clone the project on your local machine and start installing the dependencies. Use the following command in order to 
clone the repository.

.. code-block:: shell

  $ git clone https://github.com/dbmqproject/dbmq.git/

Once it's done, everything would be ready for the virtual environment. We are keeping up with ``virtualenv`` package
which is also available on 
`PyPi
<https://pypi.org/>`_. In this example, we are using ``python3.8`` with ``pip3``. Make sure you have already installed 
them on your machine, then run the following command to install the ``virtualenv`` on your machine.

.. code-block:: shell

   $ pip3 install virtualenv

Once it's done, make sure you are already in the cloned DBMQ repository on your machine with the following command and 
create a new virtualenv named ``env`` within the directory. We have also activate our environment using the ``source`` command as follows.

.. code-block:: shell

   $ pwd
   /path/to/dir/DBMQ/
   $ virtualenv env && source env/bin/activate

.. note::
   Some developers wish to name their virtualenv ``.venv`` or ``.env``. It actually makes the directory hidden which is much prettier.

Now, you are entered through your isolated environment. It's time to install the dependencies. DBMQ stores all dependencies 
in a text file named ``requirements.txt``. Run the following command and it installs all dependencies automatically.

.. code-block:: shell

   (env)$ pip install -r requirements.txt

Congratulations. Everything is ready to use. DBMQ has a default configuration that allows you to setup your applications as an 
example. It's time to crack on with the next step which is configuring our services.