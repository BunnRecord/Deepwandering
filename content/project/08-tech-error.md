+++
title = "遇到编程问题的解决"
date = 2024-09-30
updated = 2024-09-30

+++

### 使用 PyAutoGUI 时模拟鼠标点击没有反应

在点击 JiJiDown 时出现的问题。用管理员模式运行 power shell，然后运行 Python 文件即可解决。[参考](https://blog.csdn.net/Owen_goodman/article/details/112269066#:~:text=%E5%9C%A8Pycha)

### 使用 GPT-SoVITS 转换英文时报错

错误信息
```
实际输入的目标文本(切句后):
['。Yes,I do.Rafael Nadal is a famous Spanish professional tennis player.He is widely regarded as one of the greatest tennis players of all time.He has won numerous Grand Slam titles,with a particular dominance on clay courts.His rivalry with players like Roger Federer and Novak Djokovic is well-known in the sports world.']
############ 提取文本Bert特征 ############
  0%|                                                                         | 0/1 [00:00<?, ?it/s][nltk_data] Error loading averaged_perceptron_tagger: <urlopen error
[nltk_data]     [Errno 11004] getaddrinfo failed>
  0%|                                                                         | 0/1 [00:03<?, ?it/s]
处理音频时发生错误:
**********************************************************************
  Resource averaged_perceptron_tagger_eng not found.
  Please use the NLTK Downloader to obtain the resource:

  >>> import nltk
  >>> nltk.download('averaged_perceptron_tagger_eng')

  For more information see: https://www.nltk.org/data.html

  Attempted to load taggers/averaged_perceptron_tagger_eng/

  Searched in:
    - 'C:\\Users\\ghost/nltk_data'
    - 'C:\\Users\\ghost\\miniconda3\\nltk_data'
    - 'C:\\Users\\ghost\\miniconda3\\share\\nltk_data'
    - 'C:\\Users\\ghost\\miniconda3\\lib\\nltk_data'
    - 'C:\\Users\\ghost\\AppData\\Roaming\\nltk_data'
    - 'C:\\nltk_data'
    - 'D:\\nltk_data'
    - 'E:\\nltk_data'
**********************************************************************
```


进入python控制台执行 import nltk nltk.download()
[参考](https://stackoverflow.com/questions/35861482/nltk-lookup-error)

NLTK是什么？

NLTK（www.nltk.org）是在处理预料库、分类文本、分析语言结构等多项操作中最长遇到的包。其收集的大量公开数据集、模型上提供了全面、易用的接口，涵盖了分词、词性标注(Part-Of-Speech tag, POS-tag)、命名实体识别(Named Entity Recognition, NER)、句法分析(Syntactic Parse)等各项 NLP 领域的功能。

[参考](https://blog.csdn.net/qq_27586341/article/details/90029181)

