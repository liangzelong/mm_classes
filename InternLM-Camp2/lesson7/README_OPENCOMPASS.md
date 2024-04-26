---
name: 'aa'
desc: 'aa'  
language:
- 'en' 
dimension:
- 'a'
- 'examination' 
sub_dimension:
- 'a'
- 'b'
website: 'hppt://www.open-compass.org'
github: 'hppt://www.open-compass.org'
paper: 'hppt://www.open-compass.org'
release_date: 2024-04-26'
tag:
- 'tag_1'
- 'tag_2'
- 'tag_#'
download_url: hppt://www.open-compass.org'
cn: # optional, for chinese version website
    name: 'a'
    desc: 'b'
---
## Introduction
New NLP benchmarks are urgently needed to align with the rapid development of large language models (LLMs). We present C-Eval, the first comprehensive Chinese evaluation suite designed to assess advanced knowledge and reasoning abilities of foundation models in a Chinese context. C-Eval comprises multiple-choice questions across four difficulty levels: middle school, high school, college, and professional. The questions span 52 diverse disciplines, ranging from humanities to science and engineering. C-Eval is accompanied by C-Eval Hard, a subset of very challenging subjects in C-Eval that requires advanced reasoning abilities to solve. We conduct a comprehensive evaluation of the most advanced LLMs on C-Eval, including both English- and Chinese-oriented models. Results indicate that only GPT-4 could achieve an average accuracy of over 60%, suggesting that there is still significant room for improvement for current LLMs. We anticipate C-Eval will help analyze important strengths and shortcomings of foundation models, and foster their development and growth for Chinese users.

## Meta Data
The data set has

Question: The body of the question
A, B, C, D: The options which the model should choose from
Answer: (Only in dev and val set) The correct answer to the question
Explanation: (Only in dev set) The reason for choosing the answer.
## Example
Question: 对于UDP协议，如果想实现可靠传输，应在哪一层实现____
A. 数据链路层
B. 网络层
C. 传输层
D. 应用层
Answer: D

## Citation
@article{huang2023ceval,
title={C-Eval: A Multi-Level Multi-Discipline Chinese Evaluation Suite for Foundation Models}, 
    author={Huang, Yuzhen and Bai, Yuzhuo and Zhu, Zhihao and Zhang, Junlei and Zhang, Jinghan and Su, Tangjun and Liu, Junteng and Lv, Chuancheng and Zhang, Yikai and Lei, Jiayi and  Fu, Yao and Sun, Maosong and He, Junxian},
    journal={arXiv preprint arXiv:2305.08322},
    year={2023}
} 