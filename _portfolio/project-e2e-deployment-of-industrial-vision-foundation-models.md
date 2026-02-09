---
title: "End-to-End Deployment of Industrial Vision Foundation Models"
layout: single
excerpt: "Led the end-to-end benchmarking, optimization, and production deployment of an industrial vision foundation model for real-time edge inference achieving 50× lower inference latency, while also refactoring and scaling the data engineering pipeline to support rapid, production-grade iteration, accelerating data engineering workflows by 100×"
category: work
order: 2
tags: [Machine Learning, Computer Vision, Visual Quality Inspection, Edge AI]
---

## 📌 Problem
Industrial visual quality inspection and impurity detection require models that generalize from few examples while operating under strict real-time and latency constraints on edge devices. In parallel, scaling such systems demands efficient data engineering pipelines to support rapid iteration, benchmarking, and continuous improvement. Existing state-of-the-art vision foundation models (e.g., SAM with ViT-B and full precision) and legacy data workflows were too slow and fragmented for closed-loop, production-grade industrial deployment.

## 👤 Role
I led the benchmarking, optimization, and production deployment of the industrial vision foundation model for edge-based, latency-critical applications. My role included evaluating backbone and precision trade-offs, refactoring the model and inference pipeline, and driving the system from research prototype to a production-ready, closed-loop industrial deployment. Complementary to model deployment, I also refactored and productionized the internal data engineering pipeline, integrating it into our R&D department's data lakehouse architecture and enabling scalable, high-throughput data processing to support model development and evaluation.

## 🛠️ Solution
On the model side, I deployed the system using a Tiny Vision Transformer (Tiny ViT) backbone and redesigned the inference pipeline for edge efficiency. This included automatic mask generation, enhanced point-prompting, refactoring legacy implementations, merging encoder and decoder into a single ONNX graph, adding batching support, and transitioning from FP32 to FP16 and INT8 quantization.
In parallel, I re-architected the data engineering pipeline by integrating it with the data lakehouse of our R&D department and accelerating data processing workflows using a Ray cluster, dramatically improving scalability and developer iteration speed. Collectively, these optimizations transformed SAM-style segmentation from a research-grade model into an industrially viable vision foundation model for few-shot inspection.

## 📈 Impact
The optimized vision pipeline reduced edge inference latency from ~20 seconds (ViT-B, FP32) to ~400 milliseconds (Tiny ViT, INT8), achieving 50× lower inference latency, enabling autonomous, closed-loop industrial visual quality inspection. At the same time, the refactored data engineering pipeline delivered ~100× faster data workflows, significantly accelerating experimentation, benchmarking, and deployment cycles. Together, these efforts bridged research-grade foundation models and data systems into a fully production-ready industrial vision platform.
