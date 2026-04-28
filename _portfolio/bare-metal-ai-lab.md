---
title: "Bare-Metal AI Lab"
excerpt: "Local AI infrastructure lab for model serving, observability, and deployment experiments."
description: "Bare-Metal AI Lab by Ethan Nguyen is a local AI infrastructure project for model serving, observability, telemetry, quantization, and operational reliability below the API layer."
collection: portfolio
permalink: /portfolio/bare-metal-ai-lab/
---

The Bare-Metal AI Lab is my local environment for operating AI systems below the API layer.

The question behind the project is simple:

> What do you learn about AI systems when you operate the compute yourself?

Cloud APIs and managed platforms are useful. They let teams move quickly and avoid unnecessary infrastructure work.

But they also hide many of the constraints that shape real AI systems: GPU memory, model fit, quantization, queueing, service recovery, telemetry, storage, and deployment discipline.

The interesting work is not just getting a model to answer once.

The hard part is operating model capability as infrastructure.

## What it is

The lab spans a Linux RTX 3090 workstation and access to Blackwell-class desktop AI hardware when available. Public details are intentionally high-level: no hostnames, private endpoints, network topology, ports, credentials, or internal configuration.

The goal is not to collect hardware. The goal is to work closer to the systems layer underneath model capability.

The environment supports local inference and serving experiments across:

- OpenAI-compatible vLLM serving
- local model caches and quantized model variants
- NVIDIA GPU telemetry
- Prometheus-compatible metrics
- Grafana-style dashboarding
- speech and vision-language-action experiments
- full-replace deployment workflows for large models

## Models and workloads

Current experiments include:

- **Gemma 4 31B** — local vLLM-compatible serving
- **Gemma 4 26B A4B variants** — quantized/local model-fit experiments
- **Qwen 35B-class FP8/MoE** — Blackwell-class inference experiments
- **Whisper Large v3** — local speech recognition experiments
- **OpenVLA 7B** — vision-language-action inference experiments

The model names are less important than the operational pattern they force.

Large local models make the hidden parts visible.

## What becomes visible

When a model runs behind an API, it can feel abstract.

When it runs on local hardware, the constraints become concrete:

- How much memory does the model actually need?
- What context length is realistic under the current memory budget?
- How does quantization change what fits?
- What does the KV cache do under load?
- Are requests waiting or running?
- Is the bottleneck compute, memory, disk, or service startup?
- What metrics would tell me before the system fails?
- How do I replace a model cleanly when there is not enough memory to run two copies at once?

These are not theoretical questions. They change the design of the system.

A model that works in a notebook is not the same thing as a model that serves reliably. A model that fits once is not the same thing as a model that can be replaced, observed, restarted, and debugged.

That distinction matters.

## Observability

The lab includes Prometheus-compatible telemetry through GPU and system exporters, along with vLLM metrics for request and serving behavior. That makes it possible to reason about the system as it runs instead of treating inference as a black box.

For AI infrastructure, the dashboard is not decoration.

It answers operational questions:

- Is the GPU saturated?
- Is memory pressure rising?
- Are requests queueing?
- Is the serving engine healthy?
- Did a deployment actually release memory?
- Are there signs of failure before users feel them?

This is the difference between a demo and an operated system.

A demo can succeed once. An operated system has to keep succeeding.

## What it proves

Managed cloud is abstraction.

Bare metal is contact with reality.

Both are valuable. The point is not that everyone should run their own hardware. Most production systems should use managed infrastructure where it makes sense.

But if the goal is to build reliable AI systems, it helps to understand what the abstraction is hiding.

Bare metal forces attention on the unglamorous parts:

- drivers
- containers
- memory pressure
- telemetry
- model loading
- service replacement
- cache behavior
- failure recovery

These details shape whether model capability becomes useful in the real world.

That is especially true in high-trust environments, where systems need to be explainable, observable, and recoverable. The model is only one part of the product. The surrounding infrastructure determines whether people can depend on it.

The project proves infrastructure judgment: the ability to reason below the API layer, operate real compute, and understand the deployment constraints that managed platforms abstract away.

## Public safety note

This page intentionally omits hostnames, private endpoints, network topology, ports, credentials, internal configuration, and employer-provided hardware details.
