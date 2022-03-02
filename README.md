# win10版本 yolov5 deepsort 行人 车辆 跟踪 检测 计数

## 应B站上同学们要求在 win10 运行

- 更新到 python 3.9.10，请不要安装更高版本。
- 更新到 yolov5 v6.1版。使用的权重文件可以在此下载：https://github.com/ultralytics/yolov5/releases/tag/v6.1
- 更新到 CUDA 11.3+
- 建议保留 Arial.ttf 文件，或在首次运行时由 yolov5 自动下载。


## 功能
- 实现了 出/入 分别计数。
- 显示检测类别。
- 默认是 南/北 方向检测，若要检测不同位置和方向，可在 main.py 文件第13行和21行，修改2个polygon的点。
- 默认检测类别：行人、自行车、小汽车、摩托车、公交车、卡车。
- 检测类别可在 detector.py 文件第60行修改。


### 视频

bilibili

[![bilibili](https://raw.githubusercontent.com/dyh/win10_yolov5_deepsort_counting/main/cover.png)](https://www.bilibili.com/video/BV13Z4y1C7Dt/ "bilibili")


## 运行环境

- python 3.9.10，pip 22.0.3+
- pytorch 1.10.2+
- pip3 install -r requirements.txt


## 如何运行

0. 确保正确安装 python 和 CUDA

    ```
    D:\> python -V
   
    D:\> nvidia-smi
   
    D:\> nvcc -V
    ```

1. 下载代码

    ```
    D:\> git clone https://github.com/dyh/win10_yolov5_deepsort_counting.git
    ```
   
   > 因此repo包含weights和mp4文件，若 git clone 速度慢，可直接下载zip文件：https://github.com/dyh/win10_yolov5_deepsort_counting/archive/refs/heads/main.zip
   
2. 进入目录

    ```
    D:\> cd win10_yolov5_deepsort_counting
    ```

3. 创建 python 虚拟环境

    ```
    D:\win10_yolov5_deepsort_counting> python -m venv venv
    ```

4. 激活虚拟环境

    ```
     D:\win10_yolov5_deepsort_counting> venv\Scripts\activate
    ```
   
5. 升级pip

    ```
     (venv) D:\win10_yolov5_deepsort_counting> python -m pip install --upgrade pip
    ```

6. 安装pytorch
   
    > 根据你的操作系统、虚拟环境以及CUDA版本，在 https://pytorch.org/get-started/locally/ 找到对应的安装命令。我的环境是 win10、pip、CUDA 11.6。
   
    ```
     (venv) D:\win10_yolov5_deepsort_counting> pip3 install torch==1.10.2+cu113 torchvision==0.11.3+cu113 torchaudio===0.10.2+cu113 -f https://download.pytorch.org/whl/cu113/torch_stable.html
    ```
   
7. 安装软件包
   
    ```
     (venv) D:\win10_yolov5_deepsort_counting> pip3 install -r requirements.txt
    ```
   
8. 在 main.py 文件中第66行，设置要检测的视频文件路径，默认为 './video/test.mp4'
   
    > 140MB的测试视频可以在这里下载：https://pan.baidu.com/s/1qHNGGpX1QD6zHyNTqWvg1w 提取码: 8ufq 
   
    ```
    capture = cv2.VideoCapture(r'video\test.mp4')
    ```
   
9. 运行程序

    ```
    (venv) D:\win10_yolov5_deepsort_counting> python main.py
    ```


## 使用框架

- https://github.com/Sharpiless/Yolov5-deepsort-inference
- https://github.com/ultralytics/yolov5/
- https://github.com/ZQPei/deep_sort_pytorch
