<div align="center">

# 📚 AI Infrastructure Notes

*Notes on LLM inference systems, written next to real experiments — from single-GPU serving to speculative decoding, engines and disaggregated deployment.*

![Focus: LLM inference](https://img.shields.io/badge/Focus-LLM%20inference-4B8BBE)
![Status: living document](https://img.shields.io/badge/Status-living%20document-brightgreen)
![Notes: written in Chinese](https://img.shields.io/badge/Notes-written%20in%20Chinese-orange)

<sub><b>English</b> · <a href="README.zh-CN.md">中文</a></sub>

</div>

## 🧭 How to read this repo

The modules are numbered in reading order: `01` fundamentals → `02` inference optimizations → `03` engines → `04` distributed deployment → `05` experiments, with `references/` collecting papers and resources. Most folders are still skeletons, so the status column below describes what is actually on disk rather than what is planned. **Every note is written in Chinese; this index is in English** (a Chinese copy of the index lives in [README.zh-CN.md](README.zh-CN.md)).

## 🗂️ Modules

| Module | What it covers | Status |
|---|---|---|
| [01-LLM-Inference-Basics](01-LLM-Inference-Basics/) | Prefill / decode, KV cache, inference bottlenecks | 📝 planned — 3 placeholder notes |
| [02-Inference-Optimization](02-Inference-Optimization/) | Speculative decoding, continuous batching, PagedAttention, prefix caching | 🚧 in progress — 1 finished article, 6 placeholders |
| [03-Inference-Engines](03-Inference-Engines/) | vLLM, SGLang | 📝 planned — folders only, no notes yet |
| [04-Distributed-Inference](04-Distributed-Inference/) | PD disaggregation, load balancing | 📝 planned — 2 placeholder notes |
| [05-Experiments](05-Experiments/) | EAGLE-4 benchmarks, PD disaggregation, GPU deployment | 📝 planned — folders only, no notes yet |
| [references](references/) | Papers and resources | 📝 planned — 1 placeholder note |

A placeholder note is a ~150-byte stub with only a title and a "to be added" marker, so it is listed here as planned, not as written.

## ✍️ Finished write-ups

One note is a full article so far — it is in Chinese.

- **[Speculative Decoding: The Evolving Philosophy of EAGLE-1 → EAGLE-4](02-Inference-Optimization/speculative-decoding/speculative-decoding-overview.md)** — starts from the memory-bandwidth bottleneck of decode, walks through what each EAGLE generation changes, and shows how the EAGLE-4 Harness makes draft-tree verification cost-aware, with a same-machine comparison of the three routes: EAGLE, DFlash and DSpark.

The `speculative-decoding/` folder also has a short [folder index](02-Inference-Optimization/speculative-decoding/README.md) (Chinese) tracking its three planned follow-ups: the EAGLE-1 → EAGLE-4 architecture details, the parallel-drafting routes DFlash / DSpark, and the EAGLE-4 Harness cost model and engine integration.

## 🔗 Companion repos

The experiments behind these notes live in separate repositories:

| Repo | Result |
|---|---|
| [eagle3-qwen3-1.7b-repro](https://github.com/lichen9240-creator/eagle3-qwen3-1.7b-repro) | EAGLE-3 reproduction on Qwen3-1.7B — **2.135×** |
| [qwen27b-spec-decode-2x5090](https://github.com/lichen9240-creator/qwen27b-spec-decode-2x5090) | Speculative decoding for a 27B model on 2× 5090 — **2.79×** with DFlash2 at C=1 |
| [llm-sizing-calculator](https://github.com/lichen9240-creator/llm-sizing-calculator) | Model and KV-cache sizing calculator — **MAPE 7.3%** |

## ⚠️ Caveats

- Speedup numbers quoted in these notes mostly come from vendor and paper **self-reports**, not independent third-party replication.
- Measurement protocols differ: model, hardware, concurrency, baseline and the reported metric (acceptance length / single-request latency / end-to-end throughput) are rarely the same across sources.
- So read every multiplier with care — and don't divide one by another.
- These notes are personal understanding; corrections are welcome.
