---
layout: page
title: projects
permalink: /projects/
description: Projects
nav: true
---
## Table of Contents

1. [Efficient Matroid-constraint-based Submodular Maximization](#submod-matroid-opt)
2. [Post-hoc Out of Distribution Detection](#post-hoc-ood)

<hr style="border:1px solid gray">
### <ins>Efficient Matroid-constraint-based Submodular Maximization</ins> <a name="submod-matroid-opt"></a>
<i class="fas fa-book"></i> *Report*: [[Click here]](Accelerated_Continuous_Greedy.pdf) <br>
<i class="fas fa-code-branch"></i> *Code:* [[Click here]](https://github.com/EeshaanJain/submodlib/tree/matroid) <br> 
**Summary:** Maximization of monotone submodular functions subject to cardinality constraints has been a topic of interest with various greedy algorithms, with many of these algorithms achieving a $$\Big(1 - \frac{1}{e}\Big)$$ approximation on the optimal solution (OPT) at high computational speeds. However, these variants of classical greedy do not work well on matroid constraints, and only provide a $$\frac{1}{2}$$ approximation of OPT. To overcome this, CONTINUOUS-GREEDY was introduced in \cite{cont} which gives a $$\Big(1-\frac{1}{e} -\epsilon\Big)$$ approximation of OPT but it has a $$O(n^8)$$ running time. In spite of that, the algorithm is useful and generalizable. An improvement to the algorithm is ACCELERATED-CONTINUOUS-GREEDY introduced which has $$\widetilde{O}(n^2)$$ running time and is much more efficient than the previous version. The project creates  support for matroid-based optimization implementation of these two optimization algorithms along with four matroid-constraint-based submodular functions in SUBMODLIB an efficient and scalable Python library for submodular optimization in Python with a C++ optimization engine. We improve the ACCELERATED-CONTINUOUS-GREEDY procedure further, and demonstrate performance on the SAP, GAP and SWP problems.

---

### <ins>Post-hoc Out of Distribution Detection</ins><a name="post-hoc-ood"></a>
<i class="fas fa-book"></i> *Report:* [[Click here]](Post_Hoc_OOD.pdf)<br>
<i class="fab fa-slideshare"></i> *Slides:* [[Click here]](Post_Hoc_OOD_Slides.pdf)<br>
<i class="fas fa-code-branch"></i> *Code:* [[Click here]](https://github.com/ph-ood/post-hoc-ood)<br>
**Summary:** We focus on OOD detection, in a classification setting, after a classifier has already been trained (i.e., a post-hoc/post-training setting). Many popular baselines propose score functions to detect OOD
data. These score functions should assign low scores to OOD data and high scores to ID data. We introduce a Dirichlet-based scoring function which outperforms other scoring functions, is computationally cheap, can generalize across
different OOD settings and has a theoretical backing. In cases when the performance is not good
enough, we provide ways to further improve the separability between the ID and OOD data without
using a large and diverse auxiliary OOD dataset (like 80 Million Tiny Images and ImageNet-22K)
for fine-tuning, unlike many other popular approaches. We
further demonstrate that tuned margins don’t always improve the result over different non-parametric
energy-based loss functions.