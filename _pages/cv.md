---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Education
---
- B.Eng. in Software Engineering, Northwestern Polytechnical University, 2027 (expected)

Research Experience
---
* Sept 2025 - Present: Research intern, Northwestern Polytechnical University
  * **Paper: Learning to See by Looking Away: Occlusion-Robust Visual Recognition via Reasoning under Partial Observations** (CVPR 2026, score: 441 (333), to appear on arXiv)
  * Proposed a novel joint optimization framework based on the Information Bottleneck principle, integrating explanatory variables into the training objective, and validated its effectiveness by integrating it into multiple architectures (VGG, ResNet, and Vision Transformers), achieving approximately a 2% accuracy improvement on CIFAR-10/100 and ImageNet
  * Personal Contribution: developed a modular PyTorch-based network framework, designed mutual information–based loss functions with the corresponding training pipeline, and established the evaluation pipeline while conducting partial experimental validation
  * Supervisor: Dr. Yuqing Yang
* Nov 2023 - Present: Research intern, Northwestern Polytechnical University
  * **Patent: A Twin-Rotor UAV Control Method Based on Fuzzy Control and Active Disturbance Rejection Control** (Under review)
  * Personal Contribution: designed and implemented a position control strategy for the outer loop based on fuzzy logic, and developed an extended state observer and composite controller for the inner loop based on Active Disturbance Rejection Control
  * Supervisor: [Assoc. Prof. Jianlin Chen](https://teacher.nwpu.edu.cn/person/2021050012)

Projects
---
- **Human-to-Robot Handovers | ICRA 2026 RGMC Competition**, Jan 2026 – Feb 2026
  - Successfully reproduced the StereoHO SOTA method on an AIRBOT Play 6-DoF robotic arm with a G2 two-finger gripper, enabling autonomous cup handover in open environments
  - Personal Contribution: Built and optimized the hardware-software pipeline; integrated and adapted open-source frameworks such as MediaPipe Hands and Visual Hull; performed policy fine-tuning based on $\pi_{0.5}$

---

- **UAV-USV Cooperative Autonomous Search and Rescue (Project Lead)**, Jul 2025 – Jan 2026

  - Combined long-endurance VTOL capabilities with high-maneuverability quadrotor operations for coordinated task execution in complex environments
  - Personal Contribution: Developed target localization module based on back-projection; designed a Kalman filter and end-to-end spatiotemporal planning algorithm, achieving centimeter-level dynamic landing accuracy

---

- **NPUcore-BLOSSOM OS Kernel Development (Contributor, Rank #2)**, Mar 2025 – Aug 2025

  - Integrated ext4/FAT32 file systems and implemented a VFS abstraction layer; built HAL supporting both RISC-V and LoongArch architectures on virtual machines and development boards
  - Implemented system calls such as sys_clock_nanosleep and sys_copy_file_range; developed core functionalities of tools including Git, Vim, GCC, and Rustc
  - Personal Contribution: Debugged kernel issues and co-developed system calls; ported applications such as Kilo and Tetris; resolved register exception handling and trap stack overflow issues on LoongArch

---

- **VTOL Fixed-Wing UAV for Maritime Autonomous Search and Rescue (Contributor, Rank #3)**, Jul 2024 – Dec 2024

  - Designed intelligent algorithms for fully autonomous VTOL operations, including takeoff, obstacle avoidance, visual perception, dynamic target tracking, and autonomous landing
  - Personal Contribution: Designed camera projection model to decouple UAV pose from image coordinates; implemented robust visual servoing with multi-feature fusion, achieving a task success rate of 93.49%

- **National Undergraduate Innovation Training Program: Design of a Perching-Capable UAV (Project Lead)**, Sept 2024 – Jun 2025

  - Designed a dual-rotor tilting structure enabling hybrid aerial-ground mobility; completed prototype development with partially validated control algorithms through real flight tests
  - Personal Contribution: Designed outer-loop position control based on fuzzy logic; implemented inner-loop anti-disturbance control with extended state observer (ESO) and composite controller

Honors 
---
- National Scholarship, Dec 2025
- Special Scholarship for Scientific Research and Innovation, NWPU, Dec 2025
- First-class Scholarship, NWPU, Dec 2025
- Second-class Scholarship, NWPU, Dec 2024

Social Experience
---
- Served as a competition assistant, ensuring the smooth execution of all stages including submission, blind review, and presentations


Skills
---
* Language: C/C++、Python、Java、SQL、Rust
* Familiar with the Linux development environment and mainstream tools including Git, Docker, Makefile, and CMake
* Skilled in full-stack UAV development environments, specifically the PX4/Gazebo/ROS ecosystem and the ArduPilot (APM) suite
* Experienced in deployment on hardware platforms such as Jetson Orin NX, Loongson 2K1000, and StarFive VisionFive 2



