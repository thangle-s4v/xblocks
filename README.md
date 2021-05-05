# xblocks

xblocks repo for S4V edx platform
Follow those steps from <https://edx.readthedocs.io/projects/xblock-tutorial/en/latest/getting_started/prereqs.html>

Install Python (<https://www.python.org/downloads/>, it can be any version of Python, I'm currently using 3.8)

Install virtual environment (<https://virtualenv.pypa.io/en/latest/installation.html>)

Clone this repo

Create virtual environment from the current directory after cloning this repo (xblocks directory in this case)

> virtualenv venv

Run the following command to activate virtual environment

> source venv/bin/activate

In the xblocks directory, run the following command to clone the XBlock SDK repository from GitHub

> git clone <https://github.com/edx/xblock-sdk.git>

Run the following command to install the XBlock SDK requirements

> pip install -r requirements/base.txt

Run the following command to return to the xblock_development directory, where you will perform the rest of your work

> cd ..

When the requirements are installed, you are in the xblocks directory, which contains the venv and xblock-sdk subdirectories. You can now create your first XBlock.

<h2> Create an XBlock </h2>
Run the following command to create the skeleton files for the XBlock.

> xblock-sdk/bin/workbench-make-xblock

Instructions in the command window instruct you to determine a short name and a class name. Follow the guidelines in the command window to determine the names that you want to use.

<h2> Install the XBlock </h2>

In the xblocks directory, use pip to install your xblocks (in this case is s4vsimple)

> pip install -e s4vsimple

<h2> Test XBlock </h2>
Run the following command to change to the xblock-sdk directory.

> cd xblock-sdk

In the xblock-sdk directory, run the following command to create the database and the tables.

> python manage.py migrate

Run

> make install

To see the web interface of the XBlock SDK, you must run the SDK server

> python manage.py runserver

![Alt text](/images/index.png?raw=true "S4V Simple XBlock")

<h2> How to install on the server</h2>
<h3> System Administrator </h3>
To install the XBlock on your platform, add the following to your requirements.txt file:

> git+https://github.com/thangle-s4v/xblock-simplevideo.git@master#egg=simplevideo==0.0.1

<h3>Course Staff </h3>
To install the XBlock in your course, access your Advanced Module List:

> Settings -> Advanced Settings -> Advanced Module List

and add the following:

> simplevideo
