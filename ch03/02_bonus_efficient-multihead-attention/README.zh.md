# 更高效的多头注意力实现

- [mha-implementations.ipynb](mha-implementations.ipynb) 包含并比较了多头注意力的不同实现

### 摘要

下图总结了性能基准（越低越好）。

&nbsp;
#### 仅前向传递

<a href="mha-implementations.ipynb"><img src="https://sebastianraschka.com/images/LLMs-from-scratch-images/bonus/mha-benchmark/1_forward-only.webp?1" width="500px"></a>

&nbsp;
#### 前向和后向传递

<a href="mha-implementations.ipynb"><img src="https://sebastianraschka.com/images/LLMs-from-scratch-images/bonus/mha-benchmark/2_forward-and-backward.webp?1" width="500px"></a>

&nbsp;
#### 编译后的前向和后向传递

<a href="mha-implementations.ipynb"><img src="https://sebastianraschka.com/images/LLMs-from-scratch-images/bonus/mha-benchmark/3_forward-and-backward-compiled.webp?1" width="500px"></a>