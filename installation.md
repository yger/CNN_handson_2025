## Installation tips

If you are not (yet) an expert in Python installations, the first major hurdle is choosing the installation procedure.

Some key concepts you need to know before starting:
 * Python itself can be distributed and installed many, many ways.
 * Python itself does not contain many features for scientific computing, so you need to install "packages". For example
   numpy, scipy, matplotlib, spikeinterface, ... These are all examples of Python packages that aid in scientific computation.
 * All of these packages have their own dependencies which requires figuring out which versions of the dependencies work for
   the combination of packages you as the user want to use.
 * Packages can be distributed and installed in several ways (pip, conda, uv, mamba, ...) and luckily these methods of installation
   typically take care of solving the dependencies for you!
 * Installing many packages at once is challenging (because of their dependency graphs) so you need to do it in an "isolated environment" to    not destroy any previous installation. You need to see an "environment" as a sub-installation in a dedicated folder.

Choosing the installer + an environment manager + a package installer is a nightmare for beginners.

The main options are:
  * use "uv", a new, fast and simple package manager. We recommend this for beginners on every operating system.
  * use "anaconda" (or its flavors-mamba, miniconda), which does everything. Used to be very popular but theses days it is becoming
    harder to use because it is slow by default and has relatively strict licensing on the default channel (not always free anymore).
    You need to play with "community channels" to make it free again, which is complicated for beginners.
    This way is better for users in organizations that have specific licensing agrees with anaconda already in place.
  * use Python from the system or Python.org + venv + pip: good and simple idea for Linux users, but does require familiarity with
    the Python ecosystem (so good for intermediate users).

Here we propose a step by step recipe for beginners based on [**"uv"**](https://github.com/astral-sh/uv).


This recipe will install:
 * spikeinterface `full` option
 * spikeinterface-gui
 * kilosort4

into our uv venv environment.


### Quick installation using "uv"

1. On macOS and Linux. Open a terminal and do
   `curl -LsSf https://astral.sh/uv/install.sh | sh`
2. On Windows. Open an instance of the CMD prompt (Windows has many options this is the recommended one from uv)
   `powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"`
3. Exit the session and log in again.
4. Download with right click and save this file in your "Documents" folder:
    * [`beginner_requirements_rolling.txt`](https://raw.githubusercontent.com/samuelgarcia/school_spike_sorting_neuralnet_bordeaux_2025/main/installation_tips/beginner_requirements_rolling.txt) for rolling release from source.
5. Open terminal or CMD and run (**Adapt with your correct name!!**):
6. Linux `uv venv /home/samuel/.virtualenvs/si_env --python 3.12`
6. macOS `uv venv /Users/samuel/.virtualenvs/si_env --python 3.12`
6. Windows `uv venv C:\Users\samuel\.virtualenvs\si_env --python 3.12`
7. Activate your virtual environment by running:
   - Linux `source /home/samuel/.virtualenvs/si_env/bin/activate` (you should see `(si_env)` in your terminal)
   - MacOS `source  /Users/samuel/.virtualenvs/si_env/bin/activate` (you should see `(si_env)` in your terminal)
   - Windows: `C:\Users\samuel\.virtualenvs\si_env\Scripts\activate`
8. Run `uv pip install -r Documents/beginner_requirements_stable.txt`


### Check the installation

If you want to test the spikeinterface install you can:

1. Download with right click + save the file [`check_your_install.py`](https://raw.githubusercontent.com/SpikeInterface/spikeinterface/main/installation_tips/check_your_install.py)
    and put it into the "Documents" folder
2. Open the CMD Prompt (Windows) or Terminal (Mac/Linux)
3. Activate your virtual environment by running:
   - Linux `source /home/samuel/.virtualenvs/si_env/bin/activate` (you should see `(si_env)` in your terminal)
   - MacOS `source  /Users/samuel/.virtualenvs/si_env/bin/activate` (you should see `(si_env)` in your terminal)
   - Windows: `C:\Users\samuel\.virtualenvs\si_env\Scripts\activate`
4. Go to your "Documents" folder with `cd Documents` or the place where you downloaded the `check_your_install.py`
5. Run `python check_your_install.py`
6. If you are a Windows user, you should also right click + save [`cleanup_for_windows.py`](https://raw.githubusercontent.com/SpikeInterface/spikeinterface/main/installation_tips/cleanup_for_windows.py). Then transfer `cleanup_for_windows.py` into your "Documents" folder and finally run:
   ```
   python cleanup_for_windows.py
   ```

This script tests the following steps:
  * importing spikeinterface
  * running tridesclous2
  * running kilosort4 (This will not work without GPU)
  * opening the spikeinterface-gui


### VSCODE

If you do not have code editor yet, then you have to install vscode
https://code.visualstudio.com/

And when vscode is opened, please install "python" and "jupyter" plugins.
