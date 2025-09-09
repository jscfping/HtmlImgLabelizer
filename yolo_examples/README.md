



# Conda Setup for Bash on Windows

> Anaconda is primarily used for the rapid switching of Python environments,
> including different Python versions and associated dependencies.
> For lightweight or minimal environments, Miniconda is a recommended alternative. 
> 

1. Install [Anaconda](https://www.anaconda.com/download).

2. Add the following function to your `~/.profile`:
```bash
init_conda() {
    . "$HOME/anaconda3/etc/profile.d/conda.sh"
}
```

3. Verify the installation by running:
```bash
conda env list
``` 


## Environment Setup

To create and activate the conda environment, execute the following commands:

```bash
conda create --name HtmlImgLabelizer python=3.10
conda activate HtmlImgLabelizer
```

## Environment Removal

To remove the `HtmlImgLabelizer` conda environment, first activate the base environment and then run:

```bash
conda activate base
conda remove --name HtmlImgLabelizer --all
```

## Dependencies Installation

Install the required Python packages using pip:

With CUDA 12.1 support:
```bash
pip install torch==2.4.1+cu121 torchvision==0.19.1+cu121 torchaudio==2.4.1+cu121 --index-url https://download.pytorch.org/whl/cu121
pip install ultralytics==8.3.191
pip install jupyterlab==4.4.6
```

With CPU:
```bash
pip install ultralytics==8.3.191
pip install jupyterlab==4.4.6
```

## Launch JupyterLab

Navigate to the `yolo_examples` directory and start JupyterLab by running:

```bash
cd yolo_examples
jupyter lab
```


