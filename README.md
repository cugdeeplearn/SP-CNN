# 空间关系语料库自动生成

本项目使用SP-CNN模型，可对自动化生成的空间关系语料进行训练

各个库及python版本如下：

- python == 3.6.12
- keras == 2.2.4
- keras_contrib == 2.0.8
- keras_bert == 0.83.0
- tensorflow == 1.14.0


# 数据集

将需要训练的数据集分为训练数据集、测试数据集，并放如data文件夹中

数据集每个句子之间需要有空行，具体数据集结构如下：

- data
  - vocab (文件夹)
  - train.txt
  - test.txt

# 词及词频的搜集与制作

本文中选择的是人名日报语料库，其已经分好词，直接对其进行统计即可获取对应词频信息

部分搜集的词及词频示例如下：
-----------------
一个	2351951
来	2276762
也	2186100
家	2162447
说	2150271
将	2116296
中国	2105200
----------------

部分搜集的空间关系词汇示例如下：
包含/包含于：分支，支流，支脉，主流，最高峰，第一高峰，首都，省会
相接：起点，起点站，源，源头，发源地，终点，终点站
相离：相离，相隔，相距，相间，隔，相望，相峙
叠置：横贯，横渡，流贯，流过，纵贯，贯穿，横卧
东：东面，东方，东，东北北，东南南，以东，之东，东隔
南：南面，南方，南，南东东，南西西，以南，之南，南隔
----------------

# 运行

项目使用 SP-CNN模型进行训练，开始训练方法如下：

- 直接运行 train.py 文件
- 或者在命令行中输入 python train.py

关于SP-CNN模型各个训练参数设置可在 train.py 中修改，初始参数如下：

- max_len = 256
- epoches = 10
- batch_size = 64

# 结果

训练结果保存在 log 文件夹中，包括 'precision', 'recall', 'f1' 三个评价指标

- log
  - train_log.log （详细记录了所有训练过程）
  - df.csv （保存了最终的训练结果）

