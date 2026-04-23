---
title: "End-to-End Deployment of Vision-Language-Action Models"
layout: single
excerpt: "Assessed the readiness of state-of-the-art VLA models for industrial deployment across two tracks: a real-world pick-and-place setup on a UR7e cobot and a virtual counterpart running on Siemens Industrial Edge — designing the full system architecture, data pipelines, and inference stack along the way"
category: work
order: 1
description: "Assessed VLA model maturity for industrial applications through real-world and simulation-based deployment tracks, designing the full system architecture from teleoperation data collection to closed-loop edge inference"
tags: [Generative AI, VLA, Robotics, Edge AI, System Architecture]
---

## 📌 Problem
Emerging Vision-Language-Action (VLA) models promise more flexible, learning-based robot control but their maturity and readiness for industrial deployment remain largely uncharted. Two core questions motivated this project: What are the current limitations of state-of-the-art VLAs that must be addressed before they can be reliably used in industrial settings? And what system architecture is required to deploy them efficiently and robustly for real-world industrial applications?

## 👤 Role
With minimal to no guidance, I led the end-to-end technical execution across both deployment tracks — from systematic model evaluation and hardware setup through custom software development, data engineering, model training, and inference pipeline deployment on both edge hardware and simulation environments.

## 🛠️ Solution

The project was structured around two parallel tracks, sharing a common closed-loop control architecture.

#### 🤖 Track 1 — Physical Robot Deployment
We built a single-arm robotic setup using a **Universal Robots UR7e cobot** equipped with an overhead and a wrist camera, targeting a pick-and-place demonstration task. After systematically benchmarking leading open-source VLAs on simulation benchmarks (LIBERO, DROID), we selected **pi0.5** from Physical Intelligence as our deployment target.

To collect training data, we extended our hardware setup with the **LeRobot Anything U Arm** framework to enable cross-embodiment teleoperation. We then built a custom software stack to collect, process, curate, and prepare the demonstration data for fine-tuning pi0.5 on our task. The trained model was deployed on an **industrial PC (IPC)** running a custom inference pipeline that drives closed-loop control on the physical robot.

#### 🖥️ Track 2 — Edge Deployment with Isaac Sim
The second track mirrored the same closed-loop control architecture with two deliberate modifications:
- The physical robot was replaced by a **virtual robot performing the same pick-and-place task in NVIDIA Isaac Sim** — a virtual replica of our physical setup
- The inference pipeline was deployed on the **AI Inference Server on a Siemens Industrial Edge Device** rather than a standalone IPC

The system comprised two nodes: an **IPC** hosting Isaac Sim and ROS2 as the robot simulation environment, and a **Siemens Industrial Edge Device** hosting AI Inference Server with the pi0.5 model. The closed-loop control data flow operated as follows:

1. At predefined time steps, robot and camera observations were queried from Isaac Sim
2. Observations were forwarded via **ROS2 and ZeroMQ** to AI Inference Server on the Industrial Edge Device
3. pi0.5 inferred **action chunks** for each time step and returned them via **ZeroMQ** to a ROS2-based Python node
4. The Python node's robot controller received the predicted relative actions, computed **inverse dynamics**, and applied the resulting joint commands to the simulated robot

As an extension, we also implemented a **synthetic data generation pipeline in Isaac Sim** to generate training demonstrations for the policy, removing the dependency on physical teleoperation for data collection.

## 📈 Impact
The project delivered several concrete outcomes:

- **Feasibility proven on real hardware:** Demonstrated that a state-of-the-art VLA (pi0.5) can be successfully fine-tuned on custom demonstration data and deployed for real-world closed-loop robotic control on a UR7e cobot.
- **Industrial Edge compatibility validated:** Demonstrated that pi0.5 can run on the Siemens AI Inference Server on an Industrial Edge Device, establishing a viable path for low-latency VLA-based robot control within the Siemens Industrial Edge ecosystem.
- **Reusable system architecture defined:** Designed and validated an end-to-end deployment architecture — from data collection and model training to edge inference and closed-loop control — applicable across both physical and simulation-based environments.
- **Limitations and future R&D directions identified:** Current VLA performance (task success rate, precision, robustness) remains limited, but the project produced a concrete foundation and clear gap analysis to guide future research and productization efforts.
