# Python-Poetry-Dependency-Management

This repository aims to run the simplest Python project using Poetry

Poetry is a dependency management and packaging tool in Python. Poetry requires a python version 3.8 or above. 

Before installing, make sure you install Poetry in a dedicated virtual environment and not in the environment of the project that has to be managed by Poetry. This makes sure that the dependencies of Poetry itself are not uninstalled or upgraded.

Here, I have used the official installer to install Poetry. You can also install via pipx or manually. You can find the official documentation here: 
https://python-poetry.org/docs/#installing-with-the-official-installer

The following steps are specific to MacOS
### Step 1 - Installation 

Run the following command on your terminal - curl -sSL https://install.python-poetry.org | python3 -

To test the installation you can run this command: poetry --version

If the installation is right, this command will give you the version of Poetry that was installed

### Step 2 - Create a new project 

poetry new poetry_project

This command creates a new directory called 'poetry_project' with a few files in them. There are 2 files that we need to know about.

1. pyproject.toml - This is Poetry's configuration file which contains metadata like python version, dependencies and their versions 
2. poetry.lock - This file makes sure that the version of dependencies are consistent across all environments and hence, prevents changes or conflicts. Every time you update a dependency or change the version, the lock file gets updated. 

### Step 3 - Adding and managing dependencies

To add a dependency to the project, say pandas, you can run the following command:

poetry add pandas

To update pandas, you can run the following command

poetry update pandas

To update all dependencies you can run

poetry update

To remove a dependency, say pandas, run the following command

poetry remove pandas

To add a dependency, say pytest, only for development environemt, run the following command 

poetry add pytest --dev

All these commands will update the pyproject.toml and poetry.lock files

### Step 4 - Running the project using Poetry 

I have a simple Python file inside poetry_project folder which I will run using the following command 

poetry run python py_file.py

### Step 5 - Running this project in a different environment 

To run this project on an environment different from where it was created, I will first run the following command

poetry install 

This command will install all of the project's dependencies that are specified in the lock file. 

Once this is done, use poetry run to run the python file

### Step 6 - Uninstalling poetry

To uninstall poetry, run the following command

curl -sSL https://install.python-poetry.org | python3 - --uninstall
