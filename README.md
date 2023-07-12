# LLMEVAL-2 中文大语言模型评测第二期

（**LOGO**）



## 项目简介

LLMEVAL-1已经告一段落，有大量的公众用户参与了进来，为我们的评测提供了详实的数据，我们也在数据收集阶段结束后提供了详细的评测报告（https://github.com/llmeval/llmeval-1）。

然而，我们也发现由于这期评测希望更多的公众参与而在题目设计上选择了绝大多数用户都可以进行评价的问题，但是这类问题不能很好的反映模型的知识覆盖率。

因此，我们推出了LLMEVAL-2专业领域评测。LLMEVAL-2评测中以用户日常使用为主线，结合线上用户问题分布情况，重点考察不同专业本科生和研究生在日常学习和生活中，希望借助大模型得到帮助的任务。


## 数据集

12个学科分别构造领域知识测试集，出题人基于外部数据库，对每个学科领域构造对应测试题集，题型为单项选择题与问答题。

其中，每个学科设计约25-30道客观题，约10-15道主观题，合计12*40=480题。

客观题问答内容示例：

```text
"question content": "请回答工业制取氯气的原理方程式"
"answer content": "工业上通常采用氯化氢气体溶于水的方法制备氯气。具体反应式为:HCl + NaOH → NaCl + H2O + Cl-,其中NaOH为碱溶液，H+和Cl-离子在溶液中发生反应生成氯气和水。"
```

主观题问答内容示例：

```
"question content": "我是一名大学生，请问我该如何学好有机化学？请为我给出建议。" 
"answer content": "作为一名大学生学习有机化学，以下是一些建议可以帮助你更好地掌握这门学科: 1. 建立坚实的基础:在学习有机化学之前，你需要先打好化学基础知识，如物理、数学等。这样才能更好地理解有机化学中的各种概念和原理。 2. 实践操作:通过实验来加深对有机化学的理解，提高实验技能。可以选择一些简单的实验项目开始，逐渐提高自己的难度和复杂程度。 3. 阅读相关书籍和论文:阅读有机化学领域的经典著作和相关文献，了解最新的研究进展和技术发展趋势。 4. 参加课外课程和活动:参加学校组织的有机化学相关的课外活动，如讲座、研讨会等，与其他学生交流经验，扩展自己的知识面。 5. 寻求专业指导:向老师和同学请教问题，寻求帮助解决问题，及时反馈学习进度，并制定合理的学习计划和目标。"
```



## 评分标准

| 题目类型 | 评价维度 | 分值 | 评价标准描述 |
|:-----|:------|:---|:-----------|
| 客观题（如单选题或填空题） | 正确性 | 3分 | 回答内容是否正确 |
|  | 解释正确性 | 2分 | 解释是否生成错误内容 |
| 主观题（如问答题） | 准确性 | 5分 | 回答内容是否有错 |
|  | 信息量 | 3分 | 回答信息是否充足 |
|  | 流畅性 | 3分 | 回答格式语法是否正确 |
|  | 逻辑性 | 3分 | 回答逻辑是否严谨 |



## 排行榜

本次评测共评测了20个大语言模型，结果如下：

|   | 客观题 |  | 主观题 |  |  |  | 排名 |总分 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 模型名称 | 答案准确性 | 解释准确性 | 流畅性 | 准确率 | 逻辑性 | 信息量 |  |  |
| GPT4 | 2.378 (2.395) | 1.670 (1.595) | 2.895 (2.989) | 4.260 (4.545) | 2.779 (2.903) | 2.691 (2.886) | 1(1) | 86.72 (89.54) |
| GPT3.5 | 2.160 (2.138) | 1.542 (1.503) | 2.861 (3.000) | 3.822 (4.295) | 2.694 (2.818) | 2.489 (2.750) | 2(2) | 80.71 (84.69) |
| 讯飞星火 | 2.114 (2.243) | 1.557 (1.632) | 2.815 (2.977) | 3.750 (4.193) | 2.560 (2.739) | 2.196 (2.716) | 3(5) | 78.05  (82.26) |
| Baichuan-13B-Chat | 2.003 (2.013) | 1.428 (1.441) | 2.847 (2.949) | 3.727 (4.102) | 2.631 (2.778) | 2.472 (2.756) | 4(6) | 77.51 (81.82) |
| minimax-abab5 | 1.922 (1.928) | 1.443 (1.493) | 2.878 (2.989) | 3.800 (3.977) | 2.656 (2.722) | 2.478 (2.699) | 5(7) | 77.47 (80.64) |
| newbing | 2.197 (2.211) | 1.583 (1.615) | 2.796 (2.989) | 3.608 (3.875) | 2.558 (2.773) | 2.061 (2.511) | 6(4) | 77.28 (82.63) |
| claude | 1.923 (2.066) | 1.463 (1.576) | 2.680 (2.977) | 3.597 (4.125) | 2.613 (2.801) | 2.414 (2.710) | 7(3) | 75.57  (83.49) |
| moss-mars | 1.961 (1.967) | 1.465 (1.470) | 2.737 (3.000) | 3.480 (3.807) | 2.508 (2.648) | 2.229 (2.534) | 8(9) | 74.41 (79.21) |
| 天工 | 1.933 (1.961) | 1.354 (1.500) | 2.774 (2.983) | 3.520 (3.807) | 2.576 (2.682) | 2.339 (2.523) | 9(8) | 74.36  (79.31) |
| ziya-llama-13b-v1 | 1.681 (1.592) | 1.306 (1.201) | 2.804 (3.000) | 3.207 (3.364) | 2.473 (2.585) | 2.120 (2.278) | 10(13) | 69.48 (70.92) |
| 通义千问 | 1.638 (1.618) | 1.275 (1.280) | 2.776 (3.000) | 3.098 (3.239) | 2.443 (2.511) | 2.126 (2.335) | 11(12) | 68.01  (71.02) |
| 360 | 1.720 (1.678) | 1.322 (1.352) | 2.700 (2.989) | 3.022 (3.352) | 2.394 (2.608) | 2.056 (2.313) | 12(10) | 67.97 (72.86) |
| 智工大模型 | 1.680 (2.072) | 1.297 (1.516) | 2.764 (2.983) | 3.067 (4.080) | 2.427 (2.744) | 1.916 (2.631) | 13(14) | 67.27  (70.53) |
| chatglm2-6b | 1.690 (1.671) | 1.345 (1.306) | 2.758 (2.920) | 2.934 (3.011) | 2.401 (2.386) | 1.956 (2.210) | 14(17) | 67.07  (69.06) |
| Vicuna-33B | 1.567 (1.684) | 1.277 (1.270) | 2.599 (2.943) | 3.033 (3.080) | 2.440 (2.398) | 2.143 (2.199) | 15(16) | 66.53 (69.16) |
| internlm-7b | 1.655 (1.658) | 1.355 (1.174) | 2.636 (2.847) | 3.091 (3.330) | 2.295 (2.392) | 1.938 (2.233) | 16(18) | 66.52  (69.00) |
| ChatGLM | 1.602 (1.638) | 1.239 (1.280) | 2.670 (2.926) | 3.022 (3.114) | 2.374 (2.443) | 2.084 (2.278) | 17(15) | 66.05 (69.48) |
| Tigerbot-180b | 1.604 (1.592) | 1.294 (1.220) | 2.573 (2.926) | 3.079 (3.557) | 2.489 (2.602) | 1.882 (2.352) | 18(11) | 65.90 (71.77) |
| AquilaChat-7b | 1.548 (1.553) | 1.239 (1.207) | 2.710 (2.932) | 2.945 (3.136) | 2.383 (2.443) | 1.918 (2.244) | 19(19) | 64.82 (68.19) |
| belle-7b-2m | 1.484 (1.461) | 1.224 (1.164) | 2.685 (2.824) | 2.695 (3.000) | 2.347 (2.335) | 1.880 (2.131) | 20(20) | 62.98 (65.27) |

总分计算公式：
$$
总分=\frac 1 n \sum_{i=1}^n score_i
$$
其中
$$
score_i=\frac{score_{ai}}{score_{fi}}
$$
$score_{ai}$为该模型在第$i$个学科中的实际得分, $score_{fi}$为第$i$个学科的总分.

*注：括号内数值为GPT-4自动测评的打分及排名。


## 附完整报告

