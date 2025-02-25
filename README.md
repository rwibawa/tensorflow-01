# tensorflow-01

## 1. Setup for Windows Native
### 1.1 Install Miniconda:
[Miniconda Windows Installer](https://repo.anaconda.com/miniconda/Miniconda3-latest-Windows-x86_64.exe)

It will be installed in folder `C:\ProgramData\miniconda3\`.

### 1.2 Install tensorflow with GPU:
[Install tensorflow with GPU in Windows Native](https://www.tensorflow.org/install/pip#windows-native_1)

Open the Miniconda Prompt:
```cmd
# Create a new conda environment named tf with the following command.
(base) C:\Users\Ryan\>conda create --name tf python=3.9
(base) C:\Users\Ryan\>conda activate tf

(tf) C:\Users\Ryan\>conda install -c conda-forge cudatoolkit=11.2 cudnn=8.1.0

(tf) C:\Users\Ryan\>cd .\.conda\envs\tf
(tf) C:\Users\Ryan\.conda\envs\tf>python.exe -m pip install --upgrade pip

# Anything above 2.10 is not supported on the GPU on Windows Native
(tf) C:\Users\Ryan\.conda\envs\tf>python.exe -m pip install "tensorflow<2.11"

# tensorflow module was compiled with numpy 1.x, 
# so the module 2.x has to be downgraded
(tf) C:\Users\Ryan\.conda\envs\tf>pip install --upgrade "numpy<2"
```

### 1.3 Install the jupyter notebook and run it
```cmd
(tf) C:\Users\Ryan\.conda\envs\tf>conda install jupyter
(tf) C:\Users\Ryan\.conda\envs\tf>jupyter notebook --port 9999
```

## 2. Setup for WSL2
### 2.1 Install miniconda
```sh
$ mkdir -p ~/miniconda3
$ wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
$ bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
$ rm -rf ~/miniconda3/miniconda.sh
$ ~/miniconda3/bin/conda init bash
$ ~/miniconda3/bin/conda init zsh
$ source ~/miniconda3/bin/activate
$ conda init --all
```

Open a new terminal
```sh
$ conda create --name unsloth_env python=3.11 pytorch-cuda=12.1 pytorch cudatoolkit xformers -c pytorch -c nvidia -c xformers -y
$ conda activate unsloth_env
```

### 2.2. Install tensorflow
[Install tensorflow with GPU in WSL2](https://www.tensorflow.org/install/pip#windows-wsl2_1)

```sh
$ pip install --upgrade pip

# For GPU users
$ pip install tensorflow[and-cuda]
```

### 3. Tensorflow Tutorial
[Tutorial for beginner](https://www.tensorflow.org/tutorials/quickstart/beginner)