---
layout: post
title:  pufferfish privacy
date:   2021-12-29 10:40:16
description: a post describing pufferfish privacy - a generalised framework of privacy
tags: math description
categories: privacy
---
This post described the concept of the Pufferfish framework introduced here[^pf].<br>
We look over notations first:
- $$\mathcal{I}$$: The set of possible database instances.
- $$\mathfrak{Data}$$: A random variable for the true dataset, which the attacker has no knowledge of.
- $$\mathbb{S}$$: A set of potential secrets, revealing which may cause harm.
- $$\mathbb{D}$$: A conservative collection of plausible data generating distributions, i.e the set of evolution scenarios.
- $$\theta$$: A probability distribution.

The Pufferfish framework needs specification of three components:
1. $$\mathbb{S}$$: This is the explicit specification of what we would want to protect. Any statement $$s \in \mathbb S$$ may or may not be true. Essentially, $$s$$ should be in $$\mathbb S$$, if the release of the statement $$s$$ or $$\neg s$$ is harmful.
2. $$\mathbb{S}_{pairs} \subseteq \mathbb{S} \times \mathbb{S}$$: This tells us how to protect $$\mathbb{S}$$. Given a discriminative pair $$(s_i, s_j)$$, the attacker mustn't be able to know if $$s_i$$ is the true data, or if $$s_j$$ is the true data. Thus, $$s_i$$ and $$s_j$$ must be **mutually exclusive** but can be **non-exhaustive**.
3. $$\mathbb{D}$$: This is a set of conservative assumptions about how data is evolved/generated, and knowledge about potential attackers. Thus, $$\mathbb{D}$$ is a set of probability distributions over $$\mathcal{I}$$ and each $$\theta \in \mathbb D$$ corresponds to an attacker we want to protect against, and is the belief of the attacker on how the data is generated.

**Definition 1:** Given a set of potential secrets $$\mathbb{S}$$, a set of discriminative pairs $$\mathbb{S}_{pairs}$$, a set of data evolution scenarios $$\mathbb{D}$$, and a privacy parameter $$\epsilon > 0$$, an algorithm $$\mathfrak{M}$$ satsifies $$\epsilon$$-**P**uffer**F**ish$$(\mathbb{S}, \mathbb{S}_{pairs}, \mathbb{D})$$ privacy if <br>
$$\triangleright \;\forall \; \omega \in$$ range$$(\mathfrak{M})$$<br>
$$\triangleright \;\forall \;$$ pairs $$(s_i, s_j) \in \mathbb{S}_{pairs}$$<br>
$$\triangleright \;\forall \;$$ distributions $$\theta \in \mathbb D$$ for which Pr$$(s_i|\theta)\neq 0$$ and Pr$$(s_j|\theta) \neq 0$$<br>
the following holds

$$\text{Pr}(\mathfrak{M}(\mathfrak{Data})=\omega|s_i, \theta) \leq e^\epsilon \text{Pr}(\mathfrak{M}(\mathfrak{Data})=\omega|s_j, \theta)$$

$$\text{Pr}(\mathfrak{M}(\mathfrak{Data})=\omega|s_j, \theta) \leq e^\epsilon \text{Pr}(\mathfrak{M}(\mathfrak{Data})=\omega|s_i, \theta)$$


[^pf]: Kifer, Daniel, and Ashwin Machanavajjhala. "Pufferfish: A framework for mathematical privacy definitions." ACM Transactions on Database Systems (TODS) 39.1 (2014): 1-36.