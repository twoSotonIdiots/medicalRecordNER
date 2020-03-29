# -
从病历记录中识别出身体部位、症状体征等实体词汇

----------------------------------------------------
### 20200329记录
- 改进点
	1. 增加了数据。 之前由于疏忽，在航哥提醒下有增加了较多的数据。存于0329dataset文件夹中。文件夹中unlabelled数据为无标签短句数据。
	2. 使用半监督的方法
		- 参考论文：
			- `Semi-Supervised Bidirectional Long Short-Term
			Memory and Conditional Random Fields Model for
			Named-Entity Recognition Using Embeddings from
			Language Models Representations`
		- 流程：
		![无监督流程图](https://github.com/twoSotonIdiots/medicalRecordNER/raw/Deng/restrategy.png)
		- 先使用原有的数据集训练出一个model。
		- 收集所有的无标签的数据，分句，对每一条句子进行处理。
		- 设置95%为阈值。对于每句话里面不确定的词（即置信度小于1的词）进行判断，如果是高于95%，则该句子的预测结果作为新的标签数据加入到训练数据集中。
		- 将新的数据集进行训练，查看是否有效果上的提升。
	3. 结果：
		- 原始数据集：
			- 训练数据集数量：584
			- validation best f1：0.80412
		- 无监督训练：
			- 训练数据集数量：584 + 10155
			- validation best f1：0.81625

- 存疑点：
	1. 使用的半监督方法并没有很solid的学术基础。只是参考并借鉴了上述的论文的方法。
	2. 使用的类别由于加了`S-`，将类别数量从11(2 \times 5+1)改成了16(3 \times 5+1)

- 下一步计划：
	1. 尝试增量量不断的训练model
	2. 对识别出来的每一个类别都进行	
