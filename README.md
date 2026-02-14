RT-DETR Improved
An enhanced implementation of RT-DETR for object detection, By introducing the P2 high-resolution branch to preserve fine-grained features, the coordinate attention (CA) module to enhance spatial relationship modeling, and the multi-scale hole residual bottleneck (DWRC3) to capture multi-scale features through convolution with different dilation rates and reduce the false negative rate of small targets, the performance of target detection for small mathematical expressions has been significantly improved.

Quick Start
# 1. Environment Installation
## Extract the project
First, download the MathExpr-DETR project from Baidu Netdisk：MathExpr-DETR.rar
: https://pan.baidu.com/s/120PaysiTziP3j7gg15C9TA?pwd=rcbd Extraction code: rcbd
and extract it
cd MathExpr-DETR
## Install the base package
pip install -e .
## Install dependency libraries
pip install timm thop efficientnet_pytorch einops grad-cam
dill
## Install OpenMMLab toolchain
pip install -U openmim
mim install mmengine
mim install &quot;mmcv&gt;=2.0.0&quot;
# Pin NumPy version (for compatibility requirements)
pip install numpy==1.26.4
pip install PyWavelets
# 2. Dataset Preparation
Dataset Directory Structure:

    dataset/
    ├── images/
    │ ├── train/
    │ ├── val/
    │ └── test/
    └── labels/
    ├── train/
    ├── val/
    └── test/

Note: Modify the data paths in your configuration file located at:
configs/dataset/your_config.yaml
# 3. Training
Single-GPU Training:
python train.py
# 4. Validation and Testing
Validation:
python val.py
Detection (Inference):
python detect.py
# 5. Visualization
Generate Heatmaps:
python heatmap.py
Plot Results:
python plot_result.py

# Project Structure

    RT-DETR-main/
    ├── ultralytics/ # Modified Ultralytics core library
    ├── dataset/ # Dataset directory (gitignored)
    ├── configs/ # Configuration files
    ├── train.py # Training script
    ├── val.py # Validation script
    ├── detect.py # Detection/Inference script
    ├── heatmap.py # Heatmap visualization
    ├── plot_result.py # Result plotting script
    ├── requirements.txt # List of dependencies
    └── README.md # Project documentation

# Environment Requirements
Python >= 3.10
PyTorch >= 2.2.2
CUDA >= 12.1
Pre-trained Weights Download
 https://pan.baidu.com/s/1jmTz1wVjF6bg7COuVxNaQw?pwd=utpm Extraction code: utpm
Available on Baidu Netdisk. After downloading, please place the files in the weights/
directory.
