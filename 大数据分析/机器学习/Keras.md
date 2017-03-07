# Keras

[Keras官网](https://keras.io/)

[Keras-github](https://github.com/fchollet/keras)

## 安装

- 安装[anaconda](/服务器端开发/机器学习/Anaconda.md)开发环境

- 安装[tensorflow](/服务器端开发/机器学习/TensorFlow.md)环境

```cmd
conda install -c conda-forge tensorflow
```

- 安装keras

```cmd
conda install -c conda-forge keras
```

- 修改后台配置

在 **C:\Users\用户名** 路径下 有一个 **.keras** 文件夹 

修改 keras.json 文件

用theano的话，keras.json写入

```json
{
    "image_dim_ordering": "th", 
    "epsilon": 1e-07, 
    "floatx": "float32", 
    "backend": "theano"
}
```

用tensorflow的话，keras.json写入

```json
{
    "image_dim_ordering": "tf", 
    "epsilon": 1e-07, 
    "floatx": "float32", 
    "backend": "tensorflow"
}
```

- 最后确认安装

 * 打开一个命令行

 * 激活tensorflow环境：activate tf

 * 输入python打开命令行控制台

 * 执行：from keras.models import Sequential

 * 正常加载，则测试通过

