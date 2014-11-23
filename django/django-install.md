# Install Django in a virtual environment

## Install and configure `virtualenvwrapper`

```sh
pip install virtualenvwrapper

# Create a directory to hold the virtual environments.
mkdir $HOME/.virtualenvs

echo "
# Python's virtualenvwrapper-RELATED
export WORKON_HOME=$HOME/.virtualenvs
source /usr/local/bin/virtualenvwrapper.sh 
" >> ~/.bash_profile
source ~/.bash_profile
```

## Install Django in a virtual environment

Change `ENV_NAME`, below, to whatever you want to call your new virtual environment. If you want to use Python 2 in your virtual environment, remove the ``-p `which python3` `` portion.

```sh
mkvirtualenv -p `which python3` ENV_NAME
pip install Django #Current version as of 2014-10-31 is v1.7.1
```

Documentation for `virtualenv`: http://virtualenv.readthedocs.org/en/latest/virtualenv.html

Documentation for `virtualenvwrapper`: http://virtualenvwrapper.readthedocs.org/en/latest/

## Other `virtualenvwrapper` commands

- `workon` - List (`workon`) or change working virtual environments (`workon ENV_NAME`)
- `lssitepackages` - List Python packages installed in the current virtual environment.
- `rmvirtualenv ENV_NAME` - Remove a virtual environment
- `deactivate` - Switch from a virtual environment to the system-installed version of Python. (May need to `deactivate` before using `rmvirtualenv `.)

Documentation for all `virtualenvwrapper` commands: http://virtualenvwrapper.readthedocs.org/en/latest/command_ref.html
