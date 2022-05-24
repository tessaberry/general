### Seting Up Jupyter Notebooks
```
conda install ipykernel
python -m ipykernel install --user --name myenv --display-name "Python (env name)"
conda install nb_conda_kernels
```

### Actively Developing Modules and Using Jupyter Notebooks
Its often nice to be able to import a class or module into a notebook to test while developing.
If you add the following commands to the top of your notebook and run them, the imported module will update without having to reload it!
```
%load_ext autoreload
%autoreload 2
```
