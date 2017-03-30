# Keras

[Keras官网](https://keras.io/)

[Keras-github](https://github.com/fchollet/keras)

## 安装

- 安装[anaconda](/大数据分析/机器学习/Anaconda.md)开发环境

- 安装[tensorflow](/大数据分析/机器学习/TensorFlow.md)环境

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

## 基础教程

#### 编译

- **optimizers**优化器

- **loss**目标函数、损失函数

**mse**:mean_squared_error，均方差，常用的目标函数，公式为((y_pred-y_true)**2).mean()

**mae**:mean_absolute_error，绝对值均差，公式为(|y_pred-y_true|).mean()

**mape**:mean_absolute_percentage_error，绝对值均差百分比， 公式为：(|(y_true - y_pred) / clip((|y_true|),epsilon, infinite)|).mean(axis=-1) * 100，和mae的区别就是，累加的是（预测值与实际值的差）除以（剔除不介于epsilon和infinite之间的实际值)，然后求均值。

**msle**:mean_squared_logarithmic_error，均方差对数，公式为： (log(clip(y_pred, epsilon, infinite)+1)- log(clip(y_true, epsilon,infinite)+1.))^2.mean(axis=-1)，这个就是加入了log对数，剔除不介于epsilon和infinite之间的预测值与实际值之后，然后取对数，作差，平方，累加求均值。

squared_hinge 公式为：(max(1-y_true*y_pred,0))^2.mean(axis=-1)，取1减去预测值与实际值乘积的结果与0比相对大的值的平方的累加均值。

hinge 公式为：(max(1-y_true*y_pred,0)).mean(axis=-1)，取1减去预测值与实际值乘积的结果与0比相对大的值的的累加均值。

binary_crossentropy: 常说的逻辑回归, 就是常用的交叉熵函数

categorical_crossentropy: 多分类的逻辑， 交叉熵函数的一种变形吧，没看太明白

#### 训练

**训练结果**

loss，训练损失

val_loss，验证损失，你用的测试数据，val_loss就是测试损失
