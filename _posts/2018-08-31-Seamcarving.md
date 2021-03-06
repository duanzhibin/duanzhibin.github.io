---
layout: post
title:  "Seamcarving：图像变换"
categories: warping  
tags:  CG CV
author: duanzhibin
---

* content
{:toc}

# 写在开头
  看到新一届入学的学弟，难免想要考虑一下自己的处境。大学四年，匆匆忙忙。欣喜的是能够找到感兴趣的方向，虽然相见恨晚。想要把自己读论文的所思所考记录下来，未来某一天成为一代宗师，此处略去N个字。

  刚开始读论文时，搞不清论文的脉络，加上许多晦涩难懂的专有名词，很费力气。因为毫无基础，所以看所有知识点都是新的。不过熟能生巧，逐渐积累，作者的意图也就容易把握了。论文中的很多想法都是挺`exciting`的，细细品味，自是回味无穷。有时候简单的算法就能产生`surperising`结果。读论文不仅要学会其方法，更要好好琢磨如何提出问题，作者又是怎么一步一步解决问题的，其中的逻辑关系是什么。
    




## Problem
  论文的第一步会介绍问题。明白了问题是什么，问题就解决了一半。这一步我们需要考虑输入（`input`）是什么，期望的输出(`output`)是什么。

  `seamcarving`解决的问题很简单。在图片的放大（或缩小）过程中，如果`高度放大的倍数`和`宽度放大的倍数`不成比例，就会出现图片失真的现象，如何解决这种失真？翻译一下就是图片的宽度和高度可以独立变化，并且不失真。
  
  输入是一张图片，输出是一张随意放大后不失真的图片。

## Basic idea
  论文的`basic idea`往往比较简单，按照我的理解,`basic idea`是根据作者的直觉和经验提出的解决方案。至于能不能实现，怎么实现，就涉及到用什么算法，哪种算法更好的问题，需要具体实践比较解决。
  
  比如该论文的`basic idea`,图片在伸缩性变化过程中，需要改变的是对图像影响最小的一部分像素点。放大过程，这部分像素点复制；缩小过程，这部分像素点移除。

  基于上面这个`basic idea`,我们进入到下一个环节，使用算法实现想法。考虑两个核心问题，如何评价像素点对图像的影响大小？如何找出这部分像素点？ 针对第一个问题，引出能量函数，评价像素点对图像的影响大小。针对第二个问题，引出动态规划算法，找出能量和最小的那部分像素点。

## energy function
  `energy function`主要基于像素与相邻像素之间的差异定义，论文中比较了不同`energy function`产生的效果。

## BP algorithm
  使用动态规划算法求得最优解。

## result 
  实验结果还是不错的。

## 我的想法
  当然，读论文是远远不够的，`state-of-the-art`的成果不会告诉你算法会出现的问题。即使有，那也是很难解决的问题，以至于他们不想去解决。对于经典的论文，论文复现必不可少，针对复现过程中会出现的问题，可以提出改进版。

  实践中发现该算法存在的问题：在图像的变化过程中，因为有一部分像素能量和最小，所以发生变化的一直是这一部分的像素点，很容易出现局部失真的情况。针对这种状况，对已经发生变化的像素点，能量值设置为无穷大，使其不会再发生变化，可有效防止这种
  失真。


## 参考文献
   [1]  Shai Avidan, Ariel Shamir. Seam Carving for Content-Aware Image Resizing. 

  
