# AI Infrastructure Notes

LLM 推理基础设施的学习笔记：从单机推理的基本盘，到投机解码、推理引擎、分布式部署，再到实测实验。

## 目录

| 模块 | 内容 | 状态 |
|---|---|---|
| [01-LLM-Inference-Basics](01-LLM-Inference-Basics/) | Prefill / Decode、KV Cache、推理瓶颈 | 待补充 |
| [02-Inference-Optimization](02-Inference-Optimization/) | 投机解码、连续批处理、PagedAttention、前缀缓存 | 进行中 |
| [03-Inference-Engines](03-Inference-Engines/) | vLLM、SGLang | 待补充 |
| [04-Distributed-Inference](04-Distributed-Inference/) | PD 分离、负载均衡 | 待补充 |
| [05-Experiments](05-Experiments/) | EAGLE-4 压测、PD 分离、GPU 部署 | 待补充 |
| [references](references/) | 论文与资料 | 待补充 |

## 已完成的文章

- **[投机解码三大将：EAGLE-1 到 4 的变化哲学](02-Inference-Optimization/speculative-decoding/speculative-decoding-overview.md)**
  从 decode 的带宽瓶颈讲起，逐层深入到 EAGLE 四代演进与 Harness 的成本感知调度；三条路线（EAGLE / DFlash / DSpark）同台对照。

## 说明

- 笔记以个人理解为主，欢迎指正。
- 文中加速比多来自厂商与论文的公开自评，横向比较时请注意测量口径。
