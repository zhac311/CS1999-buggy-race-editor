CS1998: Buggy Race Editor
=========================

> GitHub repo: [https://github.com/RHUL-CS-Projects/CS1998-buggy-race-editor](RHUL-CS-Projects/CS1998-buggy-race-editor)
>
>
> This is the "buggy editor" component of the Foundation Year Computer Science
> project at RHUL.

Overview
--------

This is the skeleton of an application for editing a racing buggy.

It runs as a webserver so you can edit the configuration of a buggy in your
browser. The editor can then generate the data, in JSON format, that you need
to add to the
[race server](#TODO-URL-NOT-YET-PUBLISHED).

The application is written in Python3 using the
[Flask](https://palletsprojects.com/p/flask/) microframework.

> It's also written in a way which you can and should fix! You should be able
> to get it up and running (with SQLite) without needing to change the code...
> but from that point on you'll need to change pretty much everything to make
> it better (including switching away from SQLite, perhaps?). 


Developing in a browswer
------------------------

We recommend you clone/download this repo onto your own machine where you can
begin developing on it: see the installation and set up instructions below (of
course we also talk you through this at the start of the project). But if you
have problems with that, or you don't have access to your own machine, you can
work on it on [https://repl.it](https://repl.it). See the course notes or ask
for details!


Installation & set up
---------------------

Getting the editor running on your own machine differs depending on which
operating system you're using. The principles are the same, but the way to
execute them is slightly different.


### Unix and Max OS

#### Installation

When you first install the buggy editor webserver you need to install some
Python modules. Instead of installing them on your whole machine (which might
be a problem if other applications need different versions of the same
libraries) it's best to create a virtual environment just for this project, and
work inside that.

To create the virtual environment, first `cd` to the directory which contains
the application files (you might have use `git clone` to create it). Then do:

    python3 -m venv venv

This creates a directory, called `venv`, where Python will keep the library
files this virtual environment uses.

Python has created a file inside that directory that you can execute at any
time to activate the virtual environment. Once you've activated it, all
subsequent python commands operate within the scope of this environment
(instead of your whole machine).

Activate the virtual environment:

    source venv/bin/activate

Next, install the Flask library. Because you activated `venv` Flask will be
installed in this virtual environment:

    pip install -U flask

Finally, set up the database:

    python3 init_db

This creates a SQLite database in a file called `database.db`.

There's no configuration file to edit. You're ready to go!


#### Running the server

If you're not already in the project's directory, `cd` into it.

Then, if you haven't done so already, activate the virtual environment:

    source venv/bin/activate

Set the environment variable to `development`:

    export FLASK_ENV=development

Now you're ready to run the application:

    python3 app.py

The webserver is running on port 5000 (that's the default for Flask apps). If
you make a request for a web page, it will reply with one!

Go to [http://localhost:5000](http://localhost:5000) in your web browser.
You haven't specified which file you want, so you'll get the `/` route, which
(you can see this by looking in `app.py`) invokes the `index.html` template.

You can see the webserver's activity in the terminal, and the result of its
action in the browser.


#### Shutting down the server

In the terminal where the webserver is running, press Control-C. This
interrupts the server and halts the execution of the program.

If you've finished, you can deactivate the virtual environment:

    deactivate

You're done!


### Windows

#### WSL

If you're on Windows10 and you run into problems with the command below, it
might be worth enabling the [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install-win10)
(WSL).


#### Installation

TODO.

---

*RHUL CS1998 (that's a course number, not a year ;-) )*

