## Running the notebooks

### Running on cloud resources
[![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/jburel/EOSC-14176/)


### Running locally

Finally, if you would like to install the necessary requirements locally,
we suggest using Mamba:

* If you do not have any pre-existing conda installation, [install Mamba](https://mamba.readthedocs.io/en/latest/installation.html#installation) and use [mambaforge](https://github.com/conda-forge/miniforge#mambaforge). 
* In case you have a pre-existing conda installation, you can install Mamba by either:
  - Using the recommended way to install Mamba from [mambaforge](https://github.com/conda-forge/miniforge#mambaforge). This will not invalidate your conda installation, but possibly your pre-existing conda envs will be in a different location (e.g. ``/Users/USER_NAME/opt/anaconda3/envs/``) then the new mamba envs (e.g. ``/Users/USER_NAME/mambaforge/envs/``). You can verify this by running ``conda env list``. The addition of ``export CONDA_ENVS_PATH=/Users/user/opt/anaconda3/envs/`` into your ``.bashprofile`` or ``.zprofile`` file will fix this. 
  - Use the [Existing conda install](https://mamba.readthedocs.io/en/latest/installation.html#existing-conda-install) way, i.e. run ``conda install mamba -n base -c conda-forge`` whilst in the base environment. This way can take much longer time than the recommended way described above, and might not lead to a successful installation, especially if run on arm64 (Apple Silicon) OS X.

To avoid conflict with used packages, we have prepared an environment:
``environment_.yml``

Create the environment(s). 

For Windows, OS X x86_64 (NOT arm64 Apple Silicon), Linux:

    $ git clone https://github.com/jburel/EOSC-14176
    
    $ cd EOSC-14176

    $ mamba env create -f environment.yml

For OS X arm64 Apple Silicon

    $ git clone https://github.com/jburel/EOSC-14176  
    
    $ cd EOSC-14176
    
    $ CONDA_SUBDIR=osx-64 mamba env create -f environment.yml

and activate the newly created environment:

    $ conda activate eosc


Before creating a new environment, remember to deactivate the current one:

    $ conda deactivate

See also [Conda command reference](https://docs.conda.io/projects/conda/en/latest/commands.html).

The following steps are only required if you want to run the notebooks.

* If you have Anaconda installed:
  * Start Jupyter from the Anaconda-navigator
  * In the conda environment, run ``mamba install ipykernel`` (for OS X Apple Silicon ``CONDA_SUBDIR=osx-64 mamba install ipykernel``)
  * To register the environment, run ``python -m ipykernel install --user --name eosc``
  * Select the notebook you wish to run and select the ``Kernel>Change kernel>Python [conda env:eosc]`` or ``Kernel>Change kernel>eosc``
* If Anaconda is not installed:
  * Add the virtualenv as a jupyter kernel i.e. ``ipython kernel install --name "eosc" --user``
  * Open jupyter notebook i.e. ``jupyter notebook`` and select the ``eosc`` kernel or ``[conda env:eosc]`` according to what is available.

  To stop the notebook server, in the terminal where te server is running, press ``Ctrl C``. The following question will be asked in the terminal ``Shutdown this notebook server (y/[n])?``. Enter the desired choice.
  
