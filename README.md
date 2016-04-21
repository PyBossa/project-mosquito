PyBossa demo project SoySuper
=============================

SoySuper demo test project

The project has five main files:

* **project.json**: a JSON file that describes the project.
* **long_description.md**: a Markdown file with a long description of the
  project.
* **template.html**: the task presenter code.
* **tutorial.html**: a tutorial file


Testing the project
===================

You need to install the pybossa-pbs libraries. Use of
a virtual environment is recommended:

```bash
    $ virtualenv env
    $ source env/bin/activate
```

```bash
    $ pip install -r requirements.txt
```


## Creating an account in a PyBossa server
Now that you've all the requirements installed in your system, you need
a PyBossa account:

*  Create an account in your PyBossa server (use [Crowdcrafting](http://crowdcrafting.org) if you want).
*  Copy your API-KEY (you can find it in your profile page).

## Configure pybossa-pbs command line

PyBossa-pbs command line tool can be configured with a config file in order to
avoid typing the API-KEY and the server every time you want to take an action
on your project. For this reason, we recommend you to actually create the
config file. For creating the file, follow the next steps:

```bash
    $ cd ~
    $ editorofyourchoice .pybossa.cfg
```

That will create a file. Now paste the following:

```ini
[default]
server: http://yourpybossaserver.com
apikey: yourapikey
```

Save the file, and you are done! From now on, pybossa-pbs will always use the
default section to run your commands.

## Create the project

Now that we've everything in place, creating the project is as simple as
running this command:

```bash
    $ pbs create_project
```

## Adding some tasks

### Using a CSV file for adding tasks

This is very simple too, thanks to pbs:

```bash
    $ pbs add_tasks --tasks-file tasks.csv
```
You'll get a progress bar with the tasks being uploaded. Now your project has
some tasks in the server to be processed by the volunteers.

## Finally, add the task presenter, tutorial and long description

Now that we've some data to process, let's add to our project the required
templates to show a better description of our project, to present the tasks to
our users, and a small tutorial for the volunteers:

```bash
    $ pbs update_project
```

Done!

