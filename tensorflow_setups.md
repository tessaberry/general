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
