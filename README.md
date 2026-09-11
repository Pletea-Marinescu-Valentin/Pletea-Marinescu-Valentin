# Valentin Pletea-Marinescu

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&height=220&section=header&text=Valentin%20Pletea-Marinescu&fontSize=42&fontAlignY=38&animation=fadeIn" width="100%" />

<br>

[![Email](https://img.shields.io/badge/Email-pletea.valentin2003%40gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:pletea.valentin2003@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Valentin%20Pletea--Marinescu-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/valentin-pletea-marinescu-437561259/)
[![GitHub](https://img.shields.io/badge/GitHub-Pletea--Marinescu--Valentin-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Pletea-Marinescu-Valentin)

</div>

---

## About Me

Embedded AI & Control Systems Engineer working across:

* computer vision and thermal/radiometric imaging
* robotics and real-time systems
* experimental control engineering
* evaluation methodology for machine learning systems
* edge AI inference
* distributed intelligent systems

I enjoy building complete systems end to end — from mathematical modelling and control design through embedded firmware and AI inference pipelines to cloud-native backend infrastructure. Recently I have been working on the measurement side of machine learning: how you know a model's output is trustworthy, not just that it looks right.

Currently pursuing a B.Sc. in Computer Science at the National University of Science and Technology POLITEHNICA Bucharest, Faculty of Automatic Control and Computer Science.

---

## Research Interests

* Embedded AI
* Computer Vision & Thermal Imaging
* Image Quality Assessment & Model Evaluation
* Robotics & Autonomous Systems
* Optimal & Adaptive Control
* Real-Time Systems
* System Identification
* Edge Inference
* Retrieval-Augmented LLM Systems
* Intelligent Monitoring Systems

---

## Selected Projects

### Thermal SR Fidelity — Radiometric Evaluation Protocol

Repository:

* https://github.com/Pletea-Marinescu-Valentin/thermal-sr-fidelity

A thermal camera is a measurement instrument: in radiometric mode every pixel
encodes a temperature. Super-resolution models are nevertheless evaluated with
metrics borrowed from the visible spectrum, none of which refers to
temperature. This project asks what those metrics miss, and builds the protocol
that measures it.

#### Implemented

* eight deterministic fidelity metrics (M0–M7) defined on 16-bit T-linear
  radiometric data and expressed in Kelvin
* hot-region preservation, invented and erased regions, thermal ordering,
  texture fabrication, boundary gradient fidelity, texture scale-invariance and
  texture correspondence
* full training and evaluation pipeline for five reconstruction methods
  (bicubic, EDSR, RRDB, SwinIR, ESRGAN) at ×4
* cluster-bootstrap confidence intervals, paired Wilcoxon tests with
  Holm–Bonferroni correction, video-disjoint splits
* differentiable multi-scale texture loss, and an ablation of what it buys

#### Key Results

* the model ranked best by LPIPS is the one that emits the most thermal texture
  the sensor never recorded
* thermal hallucination here is distributed texture fabrication, not invented
  hotspots: erased hot regions outnumber invented ones by two orders of
  magnitude
* the fabricated texture is statistically *correct* — it matches the measured
  scale-invariance to 0.044 — while carrying almost none of the measured
  signal (r = 0.039), so texture statistics cannot detect it and a
  correspondence criterion is required
* validated against phase-randomised surrogate references whose answer is known
  by construction
* 103 unit tests, including fractal metrics checked against synthetic surfaces
  of known Hurst exponent

First-author paper in preparation.

---

### AI-Based Anti-Plagiarism Monitoring System

Real-time multimodal exam monitoring platform combining:

* gaze estimation using MediaPipe Face Mesh (468 landmarks)
* adaptive Kalman filtering
* dual YOLOv8 pipelines for smartphone and smartwatch detection
* audio activity detection + Romanian speech transcription
* motorized gimbal classroom scanning
* multi-student orchestration and event persistence

#### Key Results

* 25+ FPS CPU-only inference
* <820 MB RAM usage
* 92.4% gaze-direction accuracy
* 88.6% smartphone detection accuracy
* 92.5% smartwatch detection accuracy
* fully local GDPR-oriented processing

#### Publication

First-author paper published at RoEduNet 2025 (ISI Indexed Conference).

Repository:

* private research repository
* extended into a 70+ page Bachelor's thesis

---

### Hold My Coffee — Active Stabilization Platform

Repository:

* https://github.com/Pletea-Marinescu-Valentin/Stabilization-Platform

3-DOF active beverage stabilization platform designed for experimental
comparison of classical, optimal and adaptive control strategies.

#### Features

* dual-MCU architecture
* Teensy 4.1 + Arduino UNO
* BLDC FOC motor control via Moteus drivers
* FDCAN communication
* N4SID system identification
* reduced-order modeling
* disturbance rejection benchmarking
* experimental controller comparison on real hardware

#### Implemented Controllers

* PID
* RST
* LQG
* MRAC

#### Additional Work

* automated testing framework
* custom Composite Performance Assessment (CPA) metric
* MATLAB identification + simulation pipeline
* embedded real-time implementation

Paper currently under preparation.

---

### Wine-Quality — Retrieval-Augmented LLM Classification

Repository:

* https://github.com/Pletea-Marinescu-Valentin/Wine-Quality

Research project exploring retrieval-augmented prompting for ordinal NLP
classification using local open-weight LLMs.

#### Implemented

* class-balanced semantic retrieval
* frozen sentence embeddings
* retrieval-augmented prompting
* semantic nearest-neighbor search
* comparative evaluation across open-weight LLMs

#### Evaluated Models

* Mistral
* Gemma
* Qwen

#### Results

Achieved ~90% classification accuracy without model fine-tuning.

Paper under preparation.

---

## Experience

### Proposal Engineer — Honeywell

**May 2026 – Present**

---

### Research Assistant — POLITEHNICA Bucharest

**May 2025 – Present**

Worked on applied research projects involving:

* AI-based anti-plagiarism systems
* ESG analytics using LLMs
* retrieval-augmented document intelligence
* cloud-native AI pipelines
* distributed backend services

#### Technologies

* FastAPI
* Docker
* AWS EC2
* PostgreSQL
* Python
* LLM APIs
* embeddings & retrieval systems

---

## Publications

### A Radiometric Fidelity Protocol for Thermal Image Super-Resolution

In preparation — First Author

A deterministic protocol of eight metrics, defined on radiometric data and
expressed in Kelvin, showing that perceptual metrics reward thermal texture
fabrication.

### Anti-Plagiarism System for Exam Monitoring

RoEduNet Conference 2025 — ISI Indexed — First Author

---

## Awards & Achievements

* 🥇 1st Place — Scientific Communications Session (SCSS 2025)
* 🥇 1st Place — TechChallenge & RoboChallenge 2025 (Freestyle) & RoboTEC (Freestyle)
* 📄 First Author — RoEduNet 2025 (ISI Indexed)
* 🔧 Open Source Contributor — Rust `rencfs`

---

## Technical Stack

<div align="center">

| Domain     | Technologies                                      |
| ---------- | ------------------------------------------------- |
| Languages  | Python, C, C++, Java, TypeScript                  |
| AI / CV    | PyTorch, YOLOv8, OpenCV, MediaPipe, LLMs          |
| Scientific | NumPy, SciPy, bootstrap CI, non-parametric testing |
| Embedded   | STM32, Teensy 4.1, Arduino, FDCAN                 |
| Control    | PID, RST, LQG, MRAC, Kalman Filtering             |
| Backend    | FastAPI, Docker, PostgreSQL                       |
| Cloud      | AWS EC2, Linux, OpenShift                         |
| Frontend   | React                                             |
| Tooling    | Git, MATLAB, Simulink, LaTeX                      |

</div>

---

## GitHub Analytics

<div align="center">

<img src="http://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=Pletea-Marinescu-Valentin&theme=tokyonight" width="95%" />

<br>

<img src="http://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=Pletea-Marinescu-Valentin&theme=tokyonight" width="47%" />
<img src="http://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=Pletea-Marinescu-Valentin&theme=tokyonight" width="47%" />

<br>

<img src="http://github-profile-summary-cards.vercel.app/api/cards/stats?username=Pletea-Marinescu-Valentin&theme=tokyonight" width="47%" />
<img src="http://github-profile-summary-cards.vercel.app/api/cards/productive-time?username=Pletea-Marinescu-Valentin&theme=tokyonight&utcOffset=2" width="47%" />

<br>

<img src="https://streak-stats.demolab.com/?user=Pletea-Marinescu-Valentin&theme=tokyonight&hide_border=true" />

<br>

<img src="https://github-readme-activity-graph.vercel.app/graph?username=Pletea-Marinescu-Valentin&theme=react-dark&hide_border=true" />

</div>

---

## Contact

<div align="center">

[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:pletea.valentin2003@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/valentin-pletea-marinescu-437561259/)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Pletea-Marinescu-Valentin)

</div>

---

<div align="center">

<img src="https://raw.githubusercontent.com/Pletea-Marinescu-Valentin/Pletea-Marinescu-Valentin/output/snake.svg" />

</div>

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&height=120&section=footer" width="100%" />

</div>
