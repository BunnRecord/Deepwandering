+++
title = "OpenAI o1 相关链接"
date = 2024-09-13
updated = 2024-09-13
+++

- [官网概述](https://openai.com/index/introducing-openai-o1-preview/)
- [官网技术报告1](https://openai.com/index/learning-to-reason-with-llms/)
- [官网技术报告2](https://openai.com/index/openai-o1-mini-advancing-cost-efficient-reasoning/)
- [安全](https://openai.com/index/openai-o1-system-card/)
- [卡兹克](https://mp.weixin.qq.com/s/edpeHU_q6I4BPmHE2-daIQ) 

  猛夸，但提及了一些 Self-Play RL

- [大聪明](https://mp.weixin.qq.com/s/-DeHD6vjf0Tt5bwmeeQuXA) 

  消极，还有很多功能缺陷，花费高，更像是一个 4o 的 agent

- [特工宇宙](https://mp.weixin.qq.com/s/g-dJAfy-bWf3RiAgnTZmqA) 
  
  谨慎的看好
  提到一篇论文《Quiet-STaR: Language Models Can Teach Themselves to Think Before Speaking》。
  o1 更多是作为弥补先前大模型缺失的推理能力，而非在全方位碾压所有模型，可谓术业有专攻，选择自己合适的才是最好的。OpenAI 只做了简单的 self-play，思维模式仍然难以琢磨，很难说 o1 是好的思维模式（引用自 MetaGPT 作者吴承霖）。
  通用的提升领域能力的方法即将出现
  OpenAI 没有披露 o1 的训练细节，但最近，我们很快能够总结出泛化性强的模型能力提升之路。可预见的是，只要给出明确的任务主题（不管是写代码、角色扮演还是做设计），都能快速完成 SOTA 的迭代。
  参考链接：
  [1] https://cdn.openai.com/o1-system-card.pdf 
  [2] https://openai.com/index/openai-o1-system-card
  [3] https://openai.com/index/introducing-openai-o1-preview/
  [4] https://openai.com/index/learning-to-reason-with-llms/
  [5] Quiet-STaR：https://arxiv.org/abs/2403.09629
  [6] STaR: https://arxiv.org/abs/2203.14465
  [7] V-STaR: https://arxiv.org/abs/2402.06457

- [量子位](https://mp.weixin.qq.com/s/dnIGPzGup6d1CXB-UW99WQ)   
  o1思考起来是什么样子？可以从[官网示例 Chain of 02-thought](https://openai.com/index/learning-to-reason-with-llms/)中的编写Bash脚本的编程任务一窥究竟。



- [字母榜](https://mp.weixin.qq.com/s/vrxHuURLtSjiXkfAuJ-Ytw)

  如今已经过去了半年多，Sora迟迟未向大众开放，甚至没有推进大规模的测试。外界开始怀疑，Sora其实根本没有足够的算力支撑运行。市场研究机构Factorial Funds发布的报告认为，部署Sora需要72万张英伟达H100芯片。
9月初，《台湾经济日报》报道台积电的A16埃米级芯片已经有大客户下单，除了苹果之外，还有OpenAI。而OpenAI将用定制芯片提升Sora的视频生成能力。这似乎也印证着此前Sora遇到了算力卡点。

- [OpenAI o1 的价值意义及 RL 的 Scaling law](https://www.weibo.com/1064649941/OwPn2auby?pagetype=groupfeed)
  
  认为 o1 价值更高，以为 OpenAI 会先做这个。
  “基座大模型最大的进展，逻辑推理能力提升的效果和方法比预想的要好”。
  “如果 o1 模型能力越做越强，则可以反哺 GPT 4o 这种多模态大一统模型”，帮助 4o 升级基座模型进行优化。
  Agent很火的概念，但是没有办法实用化，因为推理能力不足，准确性不够高。
  “o1 通过Self Play增强逻辑推理能力的方向应该还有很大的发展潜力”。
  o1 一发，各公司开始卷，“OpenAI很多时候起到一个行业指路明灯的作用，往往是第一个证明某个方向是行得通的（比如ChatGPT、GPT 4、Sora、GPT 4o包括这次的o1）”，这是一个卷的好方向。
  “大语言模型最基础的能力有三种：语言理解和表达能力、世界知识存储和查询能力以及逻辑推理能力（包括数学、Coding、推理等理科能力）。”
  语言能力来自数据，世界知识含量也来自数据。
  “OpenAI o1提到了关于RL在训练和推理时候的Scaling law，并指出这与预训练时候的Scaling law具有不同特性。”

- [解释OpenAI o1模型原理](https://www.weibo.com/1233486457/OwQcNd5sB?pagetype=profilefeed)
  
  将o1投入生产要比在学术基准上取得好成绩困难得多。对于实际的推理问题，如何确定何时停止搜索？奖励函数是什么？成功的标准是什么？什么时候该在循环中调用像代码解释器这样的工具？如何将这些CPU过程的计算成本纳入考虑？他们的研究文章并没有透露太多。

  Strawberry 很容易成为一个数据飞轮。如果答案正确，整个搜索轨迹将成为一个包含正面和负面奖励的迷你训练数据集。
  
  进一步提升未来版本GPT的推理核心。
  
  感觉有戏。