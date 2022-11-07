# Simiple Conda tools for working with Tensorflow with NVIDIA GPUs
See latest version compatability here: https://www.tensorflow.org/install/pip

`requirements-gpu.txt`
```
cudnn==8.2.1
cudatoolkit==11.3.1
```
can be setup by running `conda install --yes --file requirements-gpu.txt`


# Run with GPU 
### Command Line
```
CUDA_VISIBLE_DEVICES=N,N,N python <path/your_script.py>
```

### Jupyter Notebook
```
import os
os.environ["CUDA_VISIBLE_DEVICES"]="2,3"
```
##### jupyter config
Juptyer Notbook Config

```
$ jupyter notebook --generate-config
Writing default config to: /eds/home/u405658/.jupyter/jupyter_notebook_config.py

$ vi ~/.jupyter/jupyter_notebook_config.py
 
Open the config file and uncomment and change the following lines 
Pick a port between 8000 and 9999 unique to you. This port MUST match the port in your .ssh/config
## The port the notebook server will listen on.
c.NotebookApp.port = 9015

## Token used for authenticating first-time connections to the server.
#
#  When no password is enabled, the default is to generate a new, random token.
#
#  Setting to an empty string disables authentication altogether, which is NOT
#  RECOMMENDED.
c.NotebookApp.token = ''

## Whether to open in a browser after starting. The specific browser used is
#  platform dependent and determined by the python standard library `webbrowser`
#  module, unless it is overridden using the --browser (NotebookApp.browser)
#  configuration option.
c.NotebookApp.open_browser = False
```

### Check GPUS
`nvidia-smi`


```
# run via command line
CUDA_VISIBLE_DEVICES=1,0 python my_script.py

# place env variables BEFORE `nohup` command
CUDA_VISIBLE_DEVICES=1,0 nohup python my_script.py > my_experiment.out &
```
