本项目使用Keras实现quasi Mul-BERT，在人物关系数据集上进行测试验证，其中quasi的意思为近似，因为Mul-BERT模型的论文还未发表，更多模型的细节还未知，因此为近似Mul-BERT。

## 数据集

- 共3901条标注样本，训练集：测试集=8:2
- 标注样本：`亲戚  1837年6月20日，<e1>威廉四世</e1>辞世，他的侄女<e2>维多利亚</e2>即位。`，其中`亲戚`为关系，`威廉四世`为实体1（entity_1），`维多利亚`为实体2（entity_2）。
- 每一种关系的标注数量如下图:

<p float="left" align="center">
    <img width="600" src="https://raw.githubusercontent.com/percent4/R-BERT_for_people_relation_extraction/master/data/bar_chart.png" />  
</p>

## 模型结构

<p float="left" align="center">
    <img width="600" src="https://raw.githubusercontent.com/DongPoLI/Mul-BERT/main/images/mul-bert-b.png" />  
</p>

## 运行环境

- python >= 3.6
- 第三方模块参考: `requiments.txt`

## 模型训练

```bash
$ python3 model_train.py
```

## 模型评估

```bash
$ python3 model_evalaute.py
# Model: chinese-RoBERTa-wwm-ext, weighted avgage F1 = 85.59%
```

Model: chinese-RoBERTa-wwm-ext, 详细的评估结果如下：

```
              precision    recall  f1-score   support

     unknown     0.8564    0.7990    0.8267       209
         上下级     0.7576    0.8065    0.7812        31
          亲戚     0.8235    0.5833    0.6829        24
        兄弟姐妹     0.8205    0.9412    0.8767        34
          合作     0.8772    0.8475    0.8621        59
          同人     1.0000    0.9487    0.9737        39
          同学     0.9091    0.8333    0.8696        24
          同门     0.9231    0.9231    0.9231        26
          夫妻     0.8140    0.8861    0.8485        79
          好友     0.8125    0.8667    0.8387        30
          师生     0.8000    0.8649    0.8312        37
          情侣     0.8333    0.8065    0.8197        31
          父母     0.8714    0.9531    0.9104       128
          祖孙     0.9545    0.8400    0.8936        25

    accuracy                         0.8570       776
   macro avg     0.8609    0.8500    0.8527       776
weighted avg     0.8585    0.8570    0.8559       776
```

 ## 模型预测

```bash
$ python3 model_predict.py
```


## References

- [NLP-progress Relation Extraction](http://nlpprogress.com/english/relationship_extraction.html)
- [Huggingface Transformers](https://github.com/huggingface/transformers)
- [https://github.com/wang-h/bert-relation-classification](https://github.com/wang-h/bert-relation-classification)
- [R-BERT](https://github.com/monologg/R-BERT)
- [Enriching Pre-trained Language Model with Entity Information for Relation Classification](https://arxiv.org/pdf/1905.08284.pdf)
- [Chinese-BERT-wwm](https://github.com/ymcui/Chinese-BERT-wwm)
- [Mul-BERT](https://github.com/DongPoLI/Mul-BERT)