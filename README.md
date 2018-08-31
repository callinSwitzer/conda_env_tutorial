# Managing Environments in Anaconda
Tutorial for managing conda environments


https://conda.io/docs/user-guide/tasks/manage-environments.html

1. Make sure Anaconda is installed: https://www.anaconda.com/download/


2. Create new environment (with same python version as base):

```
conda create --name myenv 
```

3. install kernel, so you can use that environment in jupyter notebook
>Activate your new environment
  ```
  source activate myenv #remove "source" for windows
  ```
>install kernelspec for all users
  ```
  python -m ipykernel install --user --name myenv
  ```
>check to see if the kernel has been installed
```
jupyter kernelspec list
```
  
>deactivate environment 
  ```
  source deactivate myenv #remove "source" for windows
  ```
>run jupyter lab
  ```
  jupyter lab
  ```
