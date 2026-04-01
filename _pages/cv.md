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
* September, 2025 - Present: Research intern, Northwestern Polytechnical University
  * **Paper: Learning to See by Looking Away: Occlusion-Robust Visual Recognition via Reasoning under Partial Observations** (CVPR 2026, score: 441 (333), to appear on arXiv)
  * Proposed a novel joint optimization framework based on the Information Bottleneck principle, integrating explanatory variables into the training objective, and validated its effectiveness by integrating it into multiple architectures (VGG, ResNet, and Vision Transformers), achieving approximately a 2% accuracy improvement on CIFAR-10/100 and ImageNet.
  * Personal Contribution: developed a modular PyTorch-based network framework, designed mutual information–based loss functions with the corresponding training pipeline, and established the evaluation pipeline while conducting partial experimental validation.
  * Supervisor: Dr. Yuqing Yang
* November, 2023 - Present: Research intern, Northwestern Polytechnical University
  * **Patent: A Twin-Rotor UAV Control Method Based on Fuzzy Control and Active Disturbance Rejection Control** (Under review)
  * Personal Contribution: designed and implemented a position control strategy for the outer loop based on fuzzy logic, and developed an extended state observer and composite controller for the inner loop based on Active Disturbance Rejection Control.
  * Supervisor: [Assoc. Prof. Jianlin Chen](https://teacher.nwpu.edu.cn/person/2021050012)

Projects
---





Skills
---
* Language: 
* Skill 2
  * Sub-skill 2.1
  * Sub-skill 2.2
  * Sub-skill 2.3
* Skill 3

Publications
---
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  

