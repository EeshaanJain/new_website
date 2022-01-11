---
layout: post
title:  singular value decomposition
date:   2022-01-10 10:40:16
description: a post describing singular value decomposition and related theorems
tags: math description
categories: linear-algebra
---
Every matrix $$\mathbf A \in \mathbb R^{m \times n}$$ has a singular value decomposition given as

$$\begin{equation}\label{eqn:svd}\mathbf{A = U\Sigma V^\top}\end{equation}$$ 

where $$\mathbf U \in \mathbb{R}^{m\times m}$$ and $$\mathbf V \in \mathbb{R}^{n\times n}$$ are orthognal matrices and $$\mathbf \Sigma\in \mathbb{R}^{m\times n}$$ is a diagonal matrix with singular values $$\sigma_i$$ on it's diagonal. Only the first $$r = \text{rank}(\mathbf A)$$ values are non-zero and are in non-increasing order, i.e

$$\begin{equation}\sigma_1 \ge \sigma_2\ge\cdots\ge\sigma_r > \sigma_{r+1} = \cdots = \sigma_{\min(m,n)} = 0 \end{equation}$$

We can also write Equation $$(\ref{eqn:svd})$$ in it's sum of outerproduct form, i.e

$$\begin{equation} \mathbf{A} = \sum_{i=1}^r \sigma_i \mathbf{u}_i\mathbf{v}_i^\top \end{equation} $$

where $$\mathbf{u}_i$$ (resp. $$\mathbf{v}_i$$) are columns of $$\mathbf U$$ (resp. $$\mathbf V$$). A point to note is that the factors in SVD provide the eigendecomposition for the following two matrices:

$$\begin{equation}\mathbf{A}^\top\mathbf A = (\mathbf{U\Sigma V^\top)^\top U\Sigma V^\top = V\Sigma^\top U^\top U \Sigma V^\top = V \Sigma^T\Sigma V^\top}\end{equation}$$
$$\begin{equation}\mathbf{A}\mathbf A^\top = \mathbf{U\Sigma V^\top(U\Sigma V^\top)^\top =  U \Sigma V^\top V\Sigma^\top U^\top= U \Sigma\Sigma^\top U^\top}\end{equation}$$

The columns of $$\mathbf V$$ (right-singular values of $$\mathbf A$$) are eigenvectors of $$\mathbf{A^\top A}$$ and the columns of $$\mathbf U$$ (left-singular values of $$\mathbf A$$) are eigenvectors of $$\mathbf{A A^\top}$$. Both $$\mathbf{\Sigma\Sigma^\top}$$ and $$\mathbf{\Sigma^\top\Sigma}$$ aren't necessarily of the same dimensions, but have diagonal values as square of the singular values (with possibly 0 trailing values). Thus, the singular values of $$\mathbf{A}$$ are the square roots of the eigenvalues of $$\mathbf{A}\mathbf A^\top$$ or $$\mathbf{A}^\top \mathbf A$$.