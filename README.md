# Managing Environments in Anaconda
Tutorial for managing conda environments


https://conda.io/docs/user-guide/tasks/manage-environments.html

## Part 0: Setup

1. Make sure Anaconda is installed: https://www.anaconda.com/download/

## Part 1: Installing a new envoironment

1. Create new environment, called "env1" with python 2.7 the package, ipython:

    ```
    conda create --name env1 python=2.7 ipython
    ```
2. Activate your new environment
    ```
    source activate env1 # remove source for windows
    ```
3. Use ipython to see if it worked

    ```
    ipython

    import sys
    sys.executable
    sys.version
    ```
    You should see something similar to this: 
    ```
    (env1) D-10-19-251-209:~ cswitzer$ ipython
    Python 2.7.15 |Anaconda, Inc.| (default, May  1 2018, 18:37:05) 
    Type "copyright", "credits" or "license" for more information.
    .
    .
    .

    In [1]: import sys

    In [2]: sys.executable
    Out[2]: '/Users/cswitzer/anaconda/envs/env1/bin/python'

    In [3]: sys.version
    Out[3]: '2.7.15 |Anaconda, Inc.| (default, May  1 2018, 18:37:05) 
    [GCC 4.2.1 Compatible Clang 4.0.1 (tags/RELEASE_401/final)]'

    ```

* Create new environment, called "env2" with python 3.7 and the package ipython
* Activate that environment. 
* Run ipython, and check to see if you're using the python version from your new environment


## Part 2: Installing a jupyter kernel, so you can select this environment in jupyter notebook
1. Install ```ipykernel``` in your new environment

    ```
    source activate env1
    conda install ipykernel
    ```


2. Use the package ```ipykernel``` to install kernel, so you can use that environment in jupyter notebook
    * Activate your new environment
        ```
        source activate myenv #remove "source" for windows
        ```

    * install kernelspec for this user

        ```
        python -m ipykernel install --user --name myenv
        ```

    * check to see if the kernel has been installed

        ```
        jupyter kernelspec list
        ```

    * deactivate environment 

        ```
        source deactivate #remove "source" for windows
        ```
    * run jupyter lab

        ```
        jupyter lab
        ```
    * check to see if you can select your new environment (Kernel -> change kernel -> env1)
    * use ```sys``` to check the environment and python version
  
  <img src="https://github.com/callinSwitzer/conda_env_tutorial/blob/master/jupyScreenshot.png" width="500">
