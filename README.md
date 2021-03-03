# Usage
 
This tutorial is based on [Jupyter Notebooks](http://jupyter.org/). Jupyter Notebook is a web-based Python development environment allowing you to combine documentation (markdown), code, and their results) into a single document. This follows a similar idea as [Mathematica](http://www.wolfram.com/mathematica/).

JupyterLab is a web-based interactive development environment for Jupyter notebooks that adds a number of quality of life additions to working with notebooks.

## Binder
Deploying Jupyter Notebooks is easy. [mybinder.org](http://mybinder.org) provides you with a free service that turns a Github repository into a collection of interactive notebooks that are accessible online.
BY default, Binder will start a Jupyter Notebook environment. You can switch to JuypterLab by appending `?urlpath=lab` to the URL.

To launch JupyterLab environment for this tutorial, go to: https://mybinder.org/v2/gh/JKU-ICG/python-visualization-tutorial/master?urlpath=lab
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/JKU-ICG/python-visualization-tutorial/master?urlpath=lab)

MyBinder installs the dependencies specified inside of the `requirements.txt` for you. We also add an extension to JupyterLab in the `postBuild` script file.


## Locally
### Setup
In this example, we use Anaconda and Python 3. 

#### Install Anaconda
Download the _Individual/Open Source Edition_ of Anaconda from: https://www.anaconda.com/download

Anaconda is a package distribution that contains the *Conda* package manager, but also a bunch of [other frequently used packages](https://docs.anaconda.com/anaconda/packages/pkg-docs/),.

We use different frameworks/libraries in this tutorial:
 * [Numpy](http://www.numpy.org/) and [Pandas](http://pandas.pydata.org/) for data manipulation
 * [Matplotlib](http://matplotlib.org/), [Seaborn](http://stanford.edu/~mwaskom/software/seaborn/), and [Altair](https://altair-viz.github.io/) for visualization
 * [Scikit-learn](http://scikit-learn.org) for simple machine learning

**Conda Environments**  
Best practice is to create an environment per project.  
Some commands to manage environments from: https://conda.io/docs/user-guide/tasks/manage-environments.html
```
conda create --name test_env python                 ... create a python environment named test_env
conda create --name jupyter_env jupyter python   ... create a python environment named jupyter_env with package jupyter

conda activate test_env                             ... activate environment test_env
conda env list                                      ... list all environments
conda list                                          ... list all packages available in environment (!= packages shipped with anaconda)
conda install numpy                                 ... install an additional package
conda install --yes --file requirements.txt         ... install packages listed in a requirements file
python -m pip install <package>                     ... install a package not aviailable via conda, also see (†)
conda deactivate                                    ... leave conda enviroment
conda env remove --name test_env                    ... remove an environment from disk
```

† See this article on [why you should prefer `python -m pip` over `pip`](https://snarky.ca/why-you-should-use-python-m-pip/).

### Start
Checkout this repo and change into the folder:
```
git clone https://github.com/JKU-ICG/python-visualization-tutorial.git
cd python-visualization-tutorial/
```

Load the conda environment from the shared `environment.yml` file:
```
conda env create -f environment.yml
```

Activate the loaded conda environment:
```
conda activate python-tutorial
```

Install Jupyter Lab extension for ipywidgets:
```
jupyter labextension install @jupyter-widgets/jupyterlab-manager
```

Launch JupyterLab:
```
jupyter lab
```
Jupyter should open a new tab with url http://localhost:8888/ and display the tutorial files.
