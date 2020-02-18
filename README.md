# Medical Record NER
1. 任务目标：从病历记录中识别出身体部位、症状体征等实体词汇
2. 数据文件夹结构&描述
```angular2
每个病例分为4个域，分别存储在4个文件夹
		一般项目
		病史特征
		诊疗过程
		出院情况
	每一个目录下存储两类文件
		***orginal.txt
			原始纯文本文件（也就是NER的输入文件）
		***.txt
			对应同名原始文件的标注结果，分四个域
				entity mention: 识别出的实体名称
				pos_b: entity mention在文件中的起始位置（从0开始编号）
				pos_e: entity mention在文件中的终止位置
				category：entity所属的类别
```
3. 参考资料链接：
 - [知乎：NLP实战-中文命名实体识别](https://zhuanlan.zhihu.com/p/61227299)
 - [论文阅读总结——Chinese NER Using Lattice LSTM](https://blog.csdn.net/qq_32728345/article/details/81264853)
 - [基于Google Bert + BiLstm+ CRF的中文实体识别](https://blog.csdn.net/yanwiicq/article/details/88352831)
 - [基于BERT预训练的中文命名实体识别TensorFlow实现](https://blog.csdn.net/macanv/article/details/85684284)
 - [半监督 Semi-NER-CRF-KNN](https://blog.csdn.net/qq_25439417/article/details/83016016?ops_request_misc=%7B%22request%5Fid%22%3A%22158202826719724839258778%22%2C%22scm%22%3A%2220140713.130056874..%22%7D&request_id=158202826719724839258778&biz_id=0&utm_source=distribute.pc_search_result.none-task)
 - [NER调研报告-zekiye-2018](https://zekizz.github.io/NER_survey_zeki.pdf)
 - [果壳中的条件随机场(CRF In A Nutshell)](https://spaces.ac.cn/archives/4695)
 - [Google Colab实战-基于Google BERT的中文命名实体识别（NER）](https://blog.csdn.net/weixin_42441790/article/details/86751031)

4. 参考github
 - [bert4keras库](https://github.com/bojone/bert4keras)
 - [ChineseNER(BiLSTM+CRF)](https://github.com/HulkZhang001/ChineseNER)
 