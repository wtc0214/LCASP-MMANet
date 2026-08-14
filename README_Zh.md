# LCASP-MMANet：一种结合金字塔结构与多模态增强的轻量级手语识别网络

## 模型简介
- **MMANet (混合多模态聚合网络，通过多分支特征提取结构融合不同语义信息)**
  
混合多模态聚合网络，通过多分支特征提取结构融合不同语义信息

- **LCASP (轻量级通道感知空间金字塔模块)**
- 
  实现多尺度上下文建模与通道特征增强，提高复杂背景下的手势检测能力

## 数据集

本项目在四个公开手语数据集上进行了实验验证：


1. ASL Dataset (American Sign Language)

🔗 https://universe.roboflow.com/meredith-lo-pmqx7/asl-project

2. Expression Dataset (Hand Gestures)

🔗 https://universe.roboflow.com/expression/expressions-tgbkg

3. ISL Dataset (Indian Sign Language)

🔗 https://universe.roboflow.com/yolov5-aqy9y/isl-using-yolov5/dataset/5


4. FSL Dataset (Filipino Sign Language)

🔗 https://universe.roboflow.com/ml-zggbn/fsl-ij1r8/dataset/1



### 3. Install Dependencies
(环境安装推荐直接使用已配置好的 YOLOv5 或 YOLOv8 环境，无需重复安装）
```bash
# Step 1.Create a virtual environment with conda
conda create -n pt121_py38 python=3.8
conda activate pt121_py38

# Step 2: Install pytorch
conda install pytorch==1.12.1 torchvision==0.13.1 torchaudio==0.12.1 cudatoolkit=11.3 -c pytorch


# Step 3: Install the remaining dependencies

pip install -r requirements.txt


# https://pytorch.org/get-started/previous-versions/
## CUDA 10.2
#conda install pytorch==1.12.1 torchvision==0.13.1 torchaudio==0.12.1 cudatoolkit=10.2 -c pytorch
## CUDA 11.3
#conda install pytorch==1.12.1 torchvision==0.13.1 torchaudio==0.12.1 cudatoolkit=11.3 -c pytorch
## CUDA 11.6
#conda install pytorch==1.12.1 torchvision==0.13.1 torchaudio==0.12.1 cudatoolkit=11.6 -c pytorch -c conda-forge
## CPU Only
#conda install pytorch==1.12.1 torchvision==0.13.1 torchaudio==0.12.1 cpuonly -c pytorch

## CUDA 11.8
#conda install pytorch==2.2.0 torchvision==0.17.0 torchaudio==2.2.0 pytorch-cuda=11.8 -c pytorch -c nvidia
## CUDA 12.1
#conda install pytorch==2.2.0 torchvision==0.17.0 torchaudio==2.2.0 pytorch-cuda=12.1 -c pytorch -c nvidia
## CPU Only
#conda install pytorch==2.2.0 torchvision==0.17.0 torchaudio==2.2.0 cpuonly -c pytorch
```


### 4. 运行训练
```bash
python train.py --data your_dataset_config.yaml
```
#### 训练脚本说明

本项目包含多个训练脚本，适用于不同任务：

4.1. **`train.py`**
  - 基础训练脚本，适用于通用目标检测任务


4.2. **`train-rtdetr.py`**
   - 用于 RT-DETR 模型的训练

4.3. **`train_Gray.py`**
   - 灰度图训练脚本，适用于单通道图像任务


### 5.测试与验证

运行以下命令进行模型验证：
```bash
python val.py
```
