# Managing Environments in Anaconda
Tutorial for managing conda environments


https://conda.io/docs/user-guide/tasks/manage-environments.html

## Part 0: Setup

1. Make sure Anaconda is installed: https://www.anaconda.com/download/

## Part 1: Installing a new environment

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
    quit
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
    
4. Deactivate the environment
    ```
    source deactivate
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

    * install kernelspec for this user

        ```
        python -m ipykernel install --user --name env1
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
    
    * Start a new jupyter noetbook
    
    * check to see if you can select your new environment (Kernel -> change kernel -> env1)
    * use ```sys``` to check the environment and python version
  
  <img src="https://github.com/callinSwitzer/conda_env_tutorial/blob/master/jupyScreenshot.png" width="500">



* install a kernel for your new environment ```env2```
* Run ```jupyter lab```, and check to see if the new environment is available


## Part 3: Using an environment.yml file

1. Download the file ```environment.yml``` <https://github.com/callinSwitzer/conda_env_tutorial/blob/master/environment.yml>
2. In terminal (or anaconda prompt), navigate to the folder where you saved this file. 
3. Create a new environment, using this file (may take ~2 min to finish)
    ```
    conda env create -f environment.yml
    ```
4. List environments
    ```
    conda env list
    ```
5. Install kernel
    ```
    source activate machLearn_env
    python -m ipykernel install --user --name machLearn_env
    ```
* Check to see if this kernel is available in Jupyter lab

## Part 4: Making an environment.yml file
1. Create an exact environment.yml file (note that this will overwrite any environment.yml file in your current directory)
```
source activate env1
conda env export > environment2.yml
```
2. Edit this exported file (by hand) to make it simpler


## Part 5: Removing unwanted environments and kernels
1. List all conda environments
```
conda env list
```
2. To remove an environment, delete it's folder

3. List kernels
```
jupyter kernelspec list
```
4. To remove a kernel, delete it's folder


*** OPTIONAL: Remove unused packages and caches
```
conda clean --all --dry-run  # do a dry run first, without deleting anything
```
```
conda clean --all # actuall delete the things
```



