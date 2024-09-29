+++
title = "LLM 原理"
date = 2024-09-11
updated = 2024-09-14

+++

看了以下一些内容。

[1. 大圣关于 GPT 原理的总结](https://axsppz4oyvj.feishu.cn/wiki/C6GFwC4JiiBQGqkKYwWcqrQwnOd)

[2. 新石器公园科普 GPT 上](https://www.bilibili.com/video/BV1yV4y1k7Tc/?spm_id_from=333.999.0.0&vd_source=19aca668850b8d744b996e0c9f666e09)

[3. 新石器公园科普 GPT 下](https://www.bilibili.com/video/BV1em4y187CU/?spm_id_from=333.999.0.0&vd_source=19aca668850b8d744b996e0c9f666e09)

[4. 渐构科普GPT](https://www.bilibili.com/video/BV1MY4y1R7EN/?spm_id_from=333.788.top_right_bar_window_history.content.click)

[5. 青工所科普GPT](https://www.bilibili.com/video/BV1uu4y1m7ak/?spm_id_from=333.1007.top_right_bar_window_history.content.click)

[6. 3B1B 深度学习第五章 Transformer 的机制](https://www.bilibili.com/video/BV13z421U7cs/?spm_id_from=333.999.0.0&vd_source=19aca668850b8d744b996e0c9f666e09)

[7. 3B1B 深度学习第六章 Transformer 的核心 注意力](https://www.bilibili.com/video/BV1TZ421j7Ke/?spm_id_from=333.788.recommend_more_video.0&vd_source=19aca668850b8d744b996e0c9f666e09)

[8. 3B1B 深度学习第七章](https://m.youtube.com/watch?v=9-Jl0dxWQs8)

[9. 一站式 LLM 底层技术原理入门指南（一篇很长的文章目前还没看）](https://s3tlxskbq3.feishu.cn/docx/NyPqdCKraoXz9gxNVCfcIFdnnAc)

该怎么去总结这一个东西呢，chatGPT，LLM。

准备分成四个部分去总结：时间线、名词、流程、问题。

### 时间线

**2017年7月**
    [Attention Is All You Need](https://arxiv.org/abs/1706.03762)。

**2018年6月**
    OpenAI训练了 [GPT1](https://cdn.openai.com/research-covers/language-unsupervised/language_understanding_paper.pdf)，训练数据 5G，参数 1.17亿，效果一般。

**2019年2月**
    OpenAI训练了 [GPT2](https://cdn.openai.com/better-language-models/language_models_are_unsupervised_multitask_learners.pdf)，训练数据 40G，参数 15 亿，效果有很大提升，但反响不大。

**2020年5月**
    OpenAI训练了 [GPT3](https://papers.nips.cc/paper/2020/hash/1457c0d6bfcb4967418bfb8ac142f64a-Abstract.html)，训练数据 45TB，参数 1750 亿，效果已经很不错了。

**2021年**
    OpenAI推出了DALL-E，这是一种深度学习模型，可以从自然语言描述中生成数字图像。

**2022年11月30日**
    OpenAI 发布名为 ChatGPT 的自然语言生成式模型。根据OpenAI的说法，预览版在前五天内收到了超过一百万的注册。

**2023年3月2日**
    OpenAI 发布了官方 ChatGPT API。

**2023年3月14日**
    OpenAI 发布了 GPT-4。

**2024年2月15日**
    OpenAI 发布了 Sora。

**2024年5月13日**
    OpenAI 发布了新模型 GPT-4o。

**2024年9月13日**
    OpenAI 发布了新模型 OpenAI o1。该模型旨在在做出反应之前花更多时间思考。他们可以通过复杂的任务进行推理，并解决比以前的科学、编码和数学模型更难的问题。

### 名词


### 流程


### 问题


### 论文及相关内容链接

[GPT-1](https://cdn.openai.com/research-covers/language-unsupervised/language_understanding_paper.pdf)

[BERT](https://arxiv.org/abs/1810.04805)。

[GPT-2](https://cdn.openai.com/better-language-models/language_models_are_unsupervised_multitask_learners.pdf)

[GPT-3](https://papers.nips.cc/paper/2020/hash/1457c0d6bfcb4967418bfb8ac142f64a-Abstract.html)

[识别态度](https://platform.openai.com/playground/p/default-adv-tweet-classifier?model=text-davinci-003)

[归纳思想](https://platform.openai.com/playground/p/default-summarize?model=text-davinci-003)

[拆分结构](https://platform.openai.com/playground/p/default-parse-data?model=text-davinci-003)

[语境内学习](https://arxiv.org/abs/2301.00234)

[GPT-3.5](https://arxiv.org/pdf/2203.02155.pdf)

[2017年的论文](https://arxiv.org/abs/1706.03762)

[2020年的论文](https://proceedings.neurips.cc/paper/2020/hash/1f89885d556929e98d3ef9b86448f951-Abstract.html)

[基辛格认为](https://hub.baai.ac.cn/view/24519)

[GPT-4 Technical Report](https://arxiv.org/abs/2303.08774)

[为什么说 GPT 是无损压缩](https://bigeagle.me/2023/03/llm-is-compression/)

[GLM-130B: An Open Bilingual Pre-trained Model](https://arxiv.org/abs/2210.02414)

[Language models can explain neurons in language models](https://openai.com/index/language-models-can-explain-neurons-in-language-models/)

[Finding Neurons in a Haystack: Case Studies with Sparse Probing](https://arxiv.org/abs/2305.01610)

[Emergent Abilities of Large Language Models](https://arxiv.org/abs/2206.07682)

[More is puferen Broken symmetry and the nature ofthe hierarchical structure of scienc](https://www.researchgate.net/publication/308012273_More_is_different_Broken_symmetry_and_the_nature_of_the_hierarchical_structure_of_science)

[Minds, brains, and programs](https://www.cambridge.org/core/journals/behavioral-and-brain-sciences/article/abs/minds-brains-and-programs/DC644B47A4299C637C89772FACC2706A)

[A Mathematical Theory ofCommunication](https://ieeexplore.ieee.org/document/6773024)

[思考，快与慢](https://book.douban.com/subject/10785583/)

[State-of-GPT](https://github.com/giachat/State-of-GPT-2023)

[State-of-GPT](https://www.youtube.com/watch?v=bZQun8Y4L2A)