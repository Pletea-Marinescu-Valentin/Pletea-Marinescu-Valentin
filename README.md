<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&height=220&section=header&text=Valentin%20Pletea-Marinescu&fontSize=42&fontAlignY=38&desc=Control%20Systems%20%C2%B7%20Embedded%20AI%20%C2%B7%20Fault-Tolerant%20Robotics&descAlignY=58&animation=fadeIn" width="100%" />

<br>

[![Email](https://img.shields.io/badge/Email-pletea.valentin2003%40gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:pletea.valentin2003@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Valentin%20Pletea--Marinescu-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/valentin-pletea-marinescu-437561259/)
[![ORCID](https://img.shields.io/badge/ORCID-0009--0000--1543--6120-A6CE39?style=for-the-badge&logo=orcid&logoColor=white)](https://orcid.org/0009-0000-1543-6120)
[![GitHub](https://img.shields.io/badge/GitHub-Pletea--Marinescu--Valentin-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Pletea-Marinescu-Valentin)

</div>

---

## About Me

Control & Embedded AI Engineer — Proposal Engineer at **Honeywell Technologies** and Researcher at
**POLITEHNICA Bucharest**.

I build complete systems end to end: identification and control design, embedded firmware,
flight software, AI inference pipelines and the evaluation that says whether any of it can be
trusted. Lately most of my work sits on the measurement side — fault detection with guaranteed
false-alarm rates, fault-tolerant flight through motor failures, and fidelity metrics that test
whether a model's output is *correct*, not just whether it *looks* right.

Every research repository here is built to be reproduced: pinned environments, unit tests against
theory, and a script behind every figure and every number in the paper.

* 🎓 B.Eng. Automatic Control and Computer Science, POLITEHNICA Bucharest (2022–2026) — thesis grade 9.87
* 🎓 M.Sc. Advanced Control and Real-Time Systems, POLITEHNICA Bucharest (2026–2028, ongoing)

---

## Research Interests

* Fault Detection & Fault-Tolerant Control
* Sequential Detection & Conformal Methods
* Optimal, Robust & Adaptive Control
* System Identification
* UAVs & PX4 Flight Software
* Embedded AI & Edge Inference
* Computer Vision & Thermal Imaging
* Model Evaluation & Image Quality Assessment
* Local LLMs for Industrial Decision Support

---

## Selected Projects

### 🚁 CTRLHEX — Fault-Tolerant Hexacopter Flight Through Motor Failures

[![repo](https://img.shields.io/badge/repo-ctrlhex-181717?logo=github)](https://github.com/Pletea-Marinescu-Valentin/ctrlhex)

A hexacopter that keeps flying when a motor stops. Built on PX4-Autopilot `main`, with control
allocation that reallocates thrust after a commanded motor failure, flown on two real vehicles and
studied in PX4 SIH simulation.

* PX4 firmware patch: **gradual motor restore** (`CA_RESTORE_SPIN`, `CA_RESTORE_TIME`), opposite
  rotor handling at ground contact, failure injection from three-position RC switches
* robust range-based height, local geofence without global position, Stabilized-mode ceiling,
  configurable kill-switch disarm delay
* board support for MicoAir H743 v2 (outputs held low at reset, 1-bit SD, `failinject` build)
* AM32 ESCs with bidirectional DShot600 + extended telemetry (per-motor RPM and current)
* flight logs of commanded motor stops on a 6S demonstrator and a 3S small hexacopter, MATLAB
  analysis, restore simulation and ablation study

---

### 🏭 Feedback-Masked Faults in Air-Handling Units

[![repo](https://img.shields.io/badge/repo-feedback--masked--faults-181717?logo=github)](https://github.com/Pletea-Marinescu-Valentin/feedback-masked-faults)
![status](https://img.shields.io/badge/IFAC%20SAFEPROCESS%202027-submitted-blue)

Integral action keeps the controlled variable at its setpoint when a sensor drifts or a component
loses capacity, so the fault disappears from the output and moves into the control effort.

* detectability analysis: how fast such faults can be found from the control-effort residual
* sequential detector with a **guaranteed false-alarm rate** — conformal p-values, a
  Dvoretzky–Kiefer–Wolfowitz correction and e-detectors
* evaluated on a public building-automation dataset; full pipeline reproduces in ~15 minutes
* 97 unit tests checked against theory (ARL ≥ 1/α, CUSUM delay, AR(1) variance inflation)

---

### ❄️ Which Fault to Repair First? — Chiller-Plant Fault Consequences

[![repo](https://img.shields.io/badge/repo-chiller--fault--consequences-181717?logo=github)](https://github.com/Pletea-Marinescu-Valentin/chiller-fault-consequences)

Fault detection systems report more faults than a maintenance team can repair. This work estimates
the operational consequence of each diagnosed fault — energy penalty against a fault-free
counterfactual and chilled-water supply deficit — from building automation data, with and without
power meters, and measures how much better repair decisions get when faults are ranked by that
estimate.

* public LBNL chiller-plant dataset, replicated on the LBNL rooftop unit
* compared against ranking by fault intensity, fault-type priority and anomaly magnitude
* decision-value metric, fully reproducible pipeline

---

### 🌡️ Thermal SR Fidelity — Radiometric Evaluation Protocol

[![repo](https://img.shields.io/badge/repo-thermal--sr--fidelity-181717?logo=github)](https://github.com/Pletea-Marinescu-Valentin/thermal-sr-fidelity)

A thermal camera is a measurement instrument: in radiometric mode every pixel encodes a
temperature. Super-resolution models are still judged with visible-spectrum metrics, none of which
refers to temperature.

* eight deterministic fidelity metrics (M0–M7) on 16-bit radiometric data, expressed in Kelvin
* five reconstruction methods at ×4 (bicubic, EDSR, RRDB, SwinIR, ESRGAN), cluster-bootstrap CIs,
  Wilcoxon + Holm–Bonferroni, video-disjoint splits
* **the model ranked best by LPIPS emits the most thermal texture the sensor never recorded**
* the fabricated texture is statistically *correct* (scale-invariance matched to 0.044) yet carries
  almost none of the measured signal (r = 0.039) — only a correspondence criterion detects it
* validated against phase-randomised surrogates whose answer is known by construction; 103 unit tests

---

### ☕ Hold My Coffee — Active Stabilization Platform & Equal-Robustness Controller Comparison

[![repo](https://img.shields.io/badge/repo-Stabilization--Platform-181717?logo=github)](https://github.com/Pletea-Marinescu-Valentin/Stabilization-Platform)

3-DOF active beverage stabilization platform whose attitude loop closes over a fieldbus — Teensy 4.1
commanding three Moteus BLDC FOC drives over FD-CAN.

* N4SID / swept-amplitude identification, order and delay chosen by cross-validation
* PID, RST, LQR, LQG and MRAC synthesized under **one identical peak sensitivity** — comparing
  structures, not how much margin each design quietly gave away
* automated benchmarking, custom Composite Performance Assessment (CPA) metric
* 🥇 1st place, Techallenge 2025 (Honeywell)

---

### 🍷 AI4WINE — Retrieval-Augmented LLMs for Wine Quality Classification

[![repo](https://img.shields.io/badge/repo-AI4WINE-181717?logo=github)](https://github.com/Pletea-Marinescu-Valentin/AI4WINE)
[![repo](https://img.shields.io/badge/repo-Wine--Quality-181717?logo=github)](https://github.com/Pletea-Marinescu-Valentin/Wine-Quality)
![status](https://img.shields.io/badge/ICSTCC%202026-accepted-brightgreen)

Ordinal quality classification from expert review text with local open-weight LLMs (Mistral, Gemma,
Qwen) — class-balanced semantic retrieval and prompting only, no fine-tuning (~90% accuracy).

The journal-track study goes further: the model reads the prose rather than exploiting price or
length, defect misses are a retrieval-coverage failure, the generative step beats its own
neighbours' majority vote, and on a disjoint corpus it holds the best macro-F1 with no retraining.

---

### 👁️ AI-Based Anti-Plagiarism Exam Monitoring

[![repo](https://img.shields.io/badge/repo-sistem--anti--plagiat-181717?logo=github)](https://github.com/Pletea-Marinescu-Valentin/sistem-anti-plagiat)
[![DOI](https://img.shields.io/badge/DOI-10.1109%2Froedunet68395.2025.11208257-blue)](https://doi.org/10.1109/roedunet68395.2025.11208257)

Real-time multimodal proctoring: MediaPipe gaze estimation with adaptive Kalman filtering, dual
YOLOv8 pipelines for smartphones and smartwatches, Romanian speech transcription, and a motorized
gimbal scanning the classroom.

* 25+ FPS CPU-only, <820 MB RAM, fully local GDPR-oriented processing
* 92.4% gaze direction · 88.6% smartphone · 92.5% smartwatch detection accuracy
* first-author paper at IEEE RoEduNet 2025; extended into the Bachelor's thesis

---

### More Projects

| Project | What it is |
| ------- | ---------- |
| [Self-Balancing-Robot-Digital-Twin](https://github.com/Pletea-Marinescu-Valentin/Self-Balancing-Robot-Digital-Twin) | Two-wheel balancer on gimbal BLDC motors — cascaded 200 Hz / 40 Hz loops on ESP32, MATLAB as live tuning console over USB or WiFi |
| [NXP Cup 2027 — RoboBadgers car](https://github.com/RoboBadgersRomania/NXPCUPA2027) | Autonomous 1/14 car: Pixy2.1 lane detection, LQR steering on Teensy 4.0, curvature-based speed profile, live tuning app |
| [scada-llm-triage](https://github.com/Pletea-Marinescu-Valentin/scada-llm-triage) | Local LLMs (3B–14B, Ollama) as an explainable triage layer over classical SCADA/ICS anomaly detectors — "ML detects, LLM explains" |
| [llm-tuner](https://github.com/Pletea-Marinescu-Valentin/llm-tuner) | Reproducible benchmark of LLM-as-tuner vs. Ziegler–Nichols, PSO and Bayesian optimization for PID, scored per plant simulation |
| [camera-gimbal-stabilizer](https://github.com/Pletea-Marinescu-Valentin/camera-gimbal-stabilizer) | Two-axis camera gimbal on STM32 with Kalman-filtered attitude |
| [rencfs](https://github.com/Pletea-Marinescu-Valentin/rencfs) | Open-source contribution to an encrypted FUSE filesystem in Rust |

---

## Experience

**Proposal Engineer — Honeywell Technologies** · Bucharest · *May 2026 – Present*

**Researcher — POLITEHNICA Bucharest** · *May 2025 – Present*
Applied research on fault detection for building systems, AI-based exam monitoring, ESG analytics
with LLMs, retrieval-augmented document intelligence and cloud-native AI pipelines
(FastAPI, Docker, AWS EC2, PostgreSQL).

---

## Publications

| Title | Venue | Status |
| ----- | ----- | ------ |
| Detectability and Calibrated Sequential Detection of Feedback-Masked Faults in Air-Handling Units | IFAC SAFEPROCESS 2027 | submitted |
| AI4WINE: A Generative Machine Learning Benchmark for Wine Quality Classification | ICSTCC 2026, Iași | accepted, in press |
| Anti-Plagiarism System for Exam Monitoring | IEEE RoEduNet 2025, Chișinău | [published](https://doi.org/10.1109/roedunet68395.2025.11208257) |
| An Open-Source Framework for Equal-Robustness Comparison of PID, RST, LQR, LQG and MRAC on a Fieldbus-Closed Stabilization Platform | — | manuscript |
| A Radiometric Fidelity Protocol for Thermal Image Super-Resolution | — | in preparation |
| Which Fault to Repair First? Estimating the Consequences of Chiller-Plant Faults from Building Automation Data | — | in preparation |

All as first author.

---

## Awards & Achievements

* 🥇 1st Place — Scientific Communications Session, ACS POLITEHNICA Bucharest, Software and Intelligent Systems (2026)
* 🏅 Honorable Mention — Scientific Communications Session, FILS POLITEHNICA Bucharest, Applied Electronics (2026)
* 🥇 1st Place — RoboTEC Freestyle, Politehnica University of Timișoara (2026)
* 🥇 1st Place — Scientific Communications Session, POLITEHNICA Bucharest (2025)
* 🥇 1st Prize — RoboChallenge Romania 2025, Freestyle Showcase University (RoboBadgers)
* 🥇 1st Place — Techallenge 2025, organized by Honeywell Technologies
* 💰 21,500 RON grant — Robotics and Programming Scholarship Fund (ING Hubs Romania & Bucharest Community Foundation, 2026)

---

## Technical Stack

<div align="center">

| Domain     | Technologies                                                        |
| ---------- | ------------------------------------------------------------------- |
| Languages  | Python, C, C++, MATLAB, Java, TypeScript, Rust                      |
| Control    | PID, RST, LQR, LQG, MRAC, Kalman filtering, N4SID, control allocation |
| Detection  | CUSUM, conformal prediction, e-detectors, bootstrap & non-parametric testing |
| Flight     | PX4-Autopilot, NuttX, SIH, ULog, QGroundControl, DShot / AM32       |
| Embedded   | STM32, Teensy 4.x, ESP32, Arduino, FD-CAN, FOC                      |
| AI / CV    | PyTorch, YOLOv8, OpenCV, MediaPipe, Ollama, sentence embeddings     |
| Backend    | FastAPI, Docker, PostgreSQL, AWS EC2, Linux, OpenShift              |
| Tooling    | Git, MATLAB / Simulink, LaTeX, pytest                               |

</div>

---

## GitHub Analytics

<div align="center">

<img src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=Pletea-Marinescu-Valentin&theme=tokyonight" width="95%" />

<br>

<img src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=Pletea-Marinescu-Valentin&theme=tokyonight" width="47%" />
<img src="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=Pletea-Marinescu-Valentin&theme=tokyonight" width="47%" />

<br>

<img src="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=Pletea-Marinescu-Valentin&theme=tokyonight" width="47%" />
<img src="https://github-profile-summary-cards.vercel.app/api/cards/productive-time?username=Pletea-Marinescu-Valentin&theme=tokyonight&utcOffset=2" width="47%" />

<br>

<img src="https://streak-stats.demolab.com/?user=Pletea-Marinescu-Valentin&theme=tokyonight&hide_border=true" />

<br>

<img src="https://github-readme-activity-graph.vercel.app/graph?username=Pletea-Marinescu-Valentin&theme=react-dark&hide_border=true" />

</div>

---

<div align="center">

<img src="https://raw.githubusercontent.com/Pletea-Marinescu-Valentin/Pletea-Marinescu-Valentin/output/snake.svg" />

</div>

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&height=120&section=footer" width="100%" />

</div>
