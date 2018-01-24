# Sentence-similarity-using-lstm-with-attention

This is an implement of bidirection LSTM with attention, using for estimate sentence similarity.

## Experiment

使用中文产品语料，通过计算相似度，对句子进行分类。

#### 一、数据准备：
  人工标注的产品和对应的句子，每个产品选出10个句子，组成数据集。
  
  训练集：同一产品下的句子互相组成正例，不同产品的句子组成负例，格式为："sentence_a  sentence_b  label"
  
  测试集：选择一个产品下的某个句子，与所有产品下的一个句子计算相似度，选取相似度最高的句子所代表的产品作为分类结果，计算top5准确率
#### 二、top5分类准确率测试结果：
  word level: 69.23%
  
  character level: 72.58%
  
  word level(bidirectional LSTM):  92.64%
  
  character level(bidirectional LSTM): 93.64%
#### 三、结果示例
  横轴为待分类的sentence_a，纵轴为计算相似度较高的sentence_b，热度图代表attention的分布，图中刻度每个数字代表该轴的一个中文词，对应关系在上方的dictionary中记录。
  
  横轴：{0: '卡通', 1: '惯性', 2: '小车'}
  
  纵轴：{0: '丹妮', 1: '益智', 2: '动手', 3: '类', 4: '玩具', 5: '-', 6: '极速', 7: '飞车', 8: '【', 9: '小车', 10: '】'}
  ![attention heat map](https://github.com/SUNCHAO1212/Sentence-similarity-using-lstm-with-attention/blob/master/figure/0.png)
#### 四、loss曲线
  
