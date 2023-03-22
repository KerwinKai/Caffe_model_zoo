# Caffe_model_zoo
Caffe model zoo, model convert by pre-train pytorch

## Start
Activate the conda environment of Python and the corresponding library dependencies
```
conda create -n py37 python=3.7
conda activate py37
pip install brocolli-caffe
git clone https://github.com/KerwinKai/Caffe2Darknet.git
git clone https://github.com/KerwinKai/Caffe_model_zoo.git

```

## Task

使用[Caffe2DarkNet](https://github.com/KerwinKai/Caffe2Darknet)，将已有的Caffe框架下的预训练模型转换至[Darknet](https://github.com/AlexeyAB/darknet)框架。提供四种轻量级网络以供选择，有以下挑战需要解决克服。

### MobileNet_v2

转换工具提示 `assert (i + 1 < layer_num and layers[i + 1]['type'] == 'ReLU')`，转换后推理未测试

### ResNet18

转换成功，推理时需要解决 `Flatten`在DarkNet上实现的问题

### shufflenet_v2

转换工具提示 `unknown type Concat`，可调研DarkNet上该层的实现方法（能否实现、有无类似功能的层），更新转换工具，转换后推理未测试

### squeezenet

转换工具提示 `unknown type Concat`，可调研DarkNet上该层的实现方法（能否实现、有无类似功能的层），更新转换工具，转换后推理未测试


## Related Links

DarkNet Original author website：https://pjreddie.com/darknet/imagenet/

DarkNet wiki：https://github.com/AlexeyAB/darknet/wiki


## Python examples using the C API
https://github.com/AlexeyAB/darknet/blob/master/darknet.py

https://github.com/AlexeyAB/darknet/blob/master/darknet_video.py