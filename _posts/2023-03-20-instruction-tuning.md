---
title: Instruction Tuning
date: 2023-03-19 23:33:26 
categories:
- LLM
tags:
- LLM
- Instruction Tuning
---

finetuning language models on a collection of tasks described via instructions substantially boosts zero-shot performance on unseen tasks.

> Paper link:  [Finetuned Language Models Are Zero-Shot Learners](https://arxiv.org/pdf/2109.01652v1.pdf)

![paper](https://pic3.zhimg.com/80/v2-9ddf840e7450ae5208ff66ea6374e902_1440w.webp)

## Instruction Tuning和Prompt Tuning的区别：

1. Prompt tuning都是针对一个任务的，比如做一个情感分析任务的prompt tuning，精调完的模型只能用于情感分析任务，而经过Instruction Tuning多任务精调后，可以用于其他任务的zero-shot。
2. Prompt tuning是去激发语言模型的补全能力，比如给出上半句生成下半句、或者做完形填空，都还是在做language model任务。而Instruction Tuning则是激发语言模型的理解能力，通过给出更明显的指令/指示，让模型去理解并做出正确的action。
3. Instruction tuning通过自然语言组成的instruction将各种自然语言任务转换为一种更加统一的形式，同时这也是一种更加贴近日常对话/聊天的形式。这种形式拉近了各种不同自然语言任务之间的距离，使得模型在in-context learning的时候更好地去"定位"，因此zero-shot性能得到提升。
4. 多种形式的instructions导致模型在精调阶段的训练模式和用户使用阶段的推理模式保持一致，instruction越多，越能模拟用户实际使用模型时千奇百怪的提问方法。

